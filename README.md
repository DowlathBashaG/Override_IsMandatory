# Override_IsMandatory

@Override :

    @Override annotation if you are not giving what will happen? is it mandatory or ignoreable?


❓ If you don't give @Override annotation in Java, what happens?

		✅ Short Answer:

		Your code will still compile and still run normally.

		@Override is NOT mandatory for the program to work.

		BUT it is highly recommended to use it!

📚 Why do we use @Override then?

		@Override helps the compiler to check if:

		You are correctly overriding a method from the superclass (or interface),

		and catch mistakes early.

🚨 Problem without @Override

		Without @Override, if you make a mistake (like wrong method signature),
		➡ the compiler won't tell you, and your method becomes a new method instead of overriding!

		❗ Example:


		class Parent {
			void show() {
				System.out.println("Parent show");
			}
		}

		class Child extends Parent {
			// Forgot to match signature, missing parentheses
			void show(int x) { // This is NOT overriding!
				System.out.println("Child show");
			}
		}
		✅ Code will compile. ✅ But show(int x) is a new method, NOT an override of Parent.show().


🌟 With @Override

		class Child extends Parent {
			@Override
			void show(int x) {  // Compiler Error! No method to override.
				System.out.println("Child show");
			}
		}
		
		➡ Now, the compiler gives an error immediately:


Error: method does not override or implement a method from a supertype

		✅ It saves you from bugs!

📜 Summary

		With @Override	Without @Override
		Compiler forces correct overriding	Compiler does not check for mistakes
		Safe and helps during refactoring	Dangerous — silent bugs possible
		Recommended best practice	Allowed but risky
		⚡ Is @Override Mandatory?

		Situation	Is @Override mandatory?
		Overriding a method	❌ No (but highly recommended)
		Implementing a method from Interface	❌ No (but recommended)
		
🧠 Best Practice

		✅ Always use @Override annotation when you intend to override a method!
		
		❝ It protects you from subtle and hard-to-find bugs. ❞

🎯 BONUS TIP
From Java 6 onward, you can even use @Override when implementing interface methods!

✅ Example:


		interface Animal {
			void sound();
		}

		class Dog implements Animal {
			@Override
			public void sound() {
				System.out.println("Bark");
			}
		}
		
🔥 Final One-Line Answer
@Override is optional but VERY highly recommended to avoid mistakes.









