
```cpp
namespace simple {
	class while_node : public cdk::basic_node {
		cdk::expression_node *_condition;
		cdk::basic_node *_block;
	public:
		while_node(int lineno, cdk::expression_node *condition, cdk::basic_node *block) : basic_node(lineno), _condition(condition), _block(block) {}

		cdk::expression_node *condition() { return _condition; }
		cdk::basic_node *basic() { return _block; }

		void accept(cdk::basic_ast_visitor *sp, int level) { 
			sp->do_while_node(this, level);
		}
	}
}
```

