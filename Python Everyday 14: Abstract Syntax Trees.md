# Python Everyday 14: Abstract Syntax Trees

Today we will see how to use 'ast' module (abstract syntax tree) to change our code by using the built-in 'compile()' function. It may be a little bit hard, but it's awesome.

```
import ast
# import pprint

fuc = """
def multi(x, y):
    return x * y

print(multi(0,2))
"""

fucAst = ast.parse(fuc)
# print(fucAst)
# <_ast.Module object at 0x108a6b4a8>


# pprint.pprint(ast.dump(fucAst))
'''
("Module(body=[FunctionDef(name='sum', args=arguments(args=[arg(arg='x', "
 "annotation=None), arg(arg='y', annotation=None)], vararg=None, "
 'kwonlyargs=[], kw_defaults=[], kwarg=None, defaults=[]), '
 "body=[Assign(targets=[Name(id='z', ctx=Store())], "
 "value=BinOp(left=Name(id='x', ctx=Load()), op=Add(), right=Name(id='y', "
 "ctx=Load()))), Return(value=Name(id='z', ctx=Load()))], decorator_list=[], "
 'returns=None)])')
 '''

class Modify(ast.NodeTransformer):
    def visit_BinOp(self, node):
        # pprint.pprint(node.__dict__)
        node.op = ast.Add()
        # pprint.pprint(node.__dict__)
        return node

modify = Modify()
modify = modify.visit(fucAst)

orgin_code = compile(ast.parse(fuc), '<string>', 'exec')
modify_code = compile(modify, '<string>', 'exec')

print("orgin_code ans: ")
exec(orgin_code)
print("------------------")
print("modify_code ans: ")
exec(modify_code)

# outputs:
'''
orgin_code ans: 
0
------------------
modify_code ans: 
2
'''
```