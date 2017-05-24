# Introduction
This style guide outlines the common coding conventions of the iOS Developers. 

# Table of Contents
* [Spacing](#spacing)
* [Comments](#comments)

# Spacing
* Indent must use 4 spaces. Be sure to set this preference in Xcode (defaults is 4 spaces).
* Method braces and other braces (if/else/switch/while etc.) must open on the same line as the statement. Braces must close on a new line.

    **For example: Objective-c**
    ```obj-c
    if (user.isHappy) {
        // Do something
    }
    else {
        // Do something else
    }
    ```
    
    **Swift**
    ```swift
    if user.isHappy == true {
        // Do something
    }
    else {
        // Do something else
    }
    ```
* Separate imports from the rest of your file by 1 space. Optionally group imports if there are many (but try to have less dependencies). Include frameworks first.

    **For example: Objective-c**
    ```obj-c
    #import <AwesomeFramework/AwesomeFramework.h>
    #import <AnotherFramework/AnotherFramework.h>

    #import "SomeDependency.h"
    #import "SomeOtherDependency.h"

    @interface MyClass
    ```
    
    **Swift**
    ```swift
    import AwesomeFramework
    import AnotherFramework
    
    class MyViewController: UIViewController {
        // class stuff here
    }
    ```
    
* In Objective-C, use one empty line between class extension and implementation in .m file.

    ``` obj-c
    @interface MyClass()

    // Properties - empty line above and below

    @end

    @implementation MyClass

    // Body - empty line above and below

    @end
    ```

* When using pragma marks leave 1 newline before and after.

    **For example: Objective-c**
    ``` obj-c
    - (void)awakeFromNib {
        [super awakeFromNib];
        // something
    }

    #pragma mark - Config Cell

    - (void)configCell {
        // something
    }
    ```
    
    **Swift**
     ```swift
     override func awakeFromNib() {
        super.awakeFromNib()
        // somthing
    }
    
    // MARK: -  Config Cell
    
    func configCell() {
        //something
    }
    ```
* Prefer using auto-synthesis. But if necessary, `@synthesize` and `@dynamic` must each be declared on new lines in the implementation.
* There should be exactly one blank line between methods to aid in visual clarity and organization.
* Whitespace within methods should separate functionality, but often there should probably be new methods.
* When doing math use a single space between operators. Unless that operator is unary in which case don't use a space.
    **For example:**
    ```obj-c
    index = index + 1;
    index++;
    index += 1;
    index--;
    ```
* Colon-aligning method invocation should often be avoided. There are cases where a method signature may have >= 3 colons and colon-aligning makes the code more readable. Please do NOT however colon align methods containing blocks because Xcode's indenting makes it illegible.

    **Good:**
    
    **objective-c**
    ```obj-c
    // blocks are easily readable
    [UIView animateWithDuration:1.0 animations:^{
        // something
    } completion:^(BOOL finished) {
        // something
    }];
    ```
    
    **swift**
    ```swift
    UIView.animate(withDuration: 1.0, animations: {
        // something
    }, completion: { finished in
        // somthing
    })
    
    ```


    **Bad:**
    
    **objective-c**    
    
    ```obj-c
    // colon-aligning makes the block indentation wacky and hard to read
    [UIView animateWithDuration:1.0
                     animations:^{
                         // something
                     }
                     completion:^(BOOL finished) {
                        // something
                     }];
    ```
    
    **swift**
    ```swift
    UIView.animate(withDuration: 1.0, 
                     animations: {
                        // something
                     }, completion: { finished in
                        // somthing
                     })
    ```
  
# Comments
* When they are needed, comments should be used to explain why a particular piece of code does something. Any comments that are used must be kept up-to-date or deleted.
* Avoid block comments inline with code, as the code should be as self-documenting as possible. Exception: This does not apply to those comments used to generate documentation.

Developing....


# References 
- [raywenderlich.com Objective-C style guide](https://github.com/raywenderlich/objective-c-style-guide)
- [NYTimes Objective-C style guide](https://github.com/NYTimes/objective-c-style-guide)
- [Robots and Pencils Objective-C style guide](https://github.com/RobotsAndPencils/objective-c-style-guide#comments)
