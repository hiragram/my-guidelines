# Action Guidelines as an iOS/Swift App Developer

## Basis of thoughts

- Humans must not do anything which a compiler can do. A compiler is far more reliable than humans are.
- Do not make extra efforts for tiny readability. The most important thing is that each parson has same understanding, not same appearance of code.
- Take advantage of IDE(Xcode) strongly.
- Do not choose a way that can crash apps on the runtime if there are another options that can prevent crash or detect errors on compilation time.

## Coding Guidelines

- Do not write type name if compiler can infer the type.

- Whether to omit `return` keyword in closure is not specified.

- Do not use abbreviations of variable name expect:
    - ViewModel -> `vm`
    - ViewController -> `vc`
    - NavigationController -> `nav`

- Add `.init` to initializer call because it enables to jump to definition of initializer directly and makes type name omittable.

- Do not extract codes as a method if it will be called in only one place.
    - In other words, do not create methods just for split a big method.

- Use empty lines flexibly.

- Omitting type name is good but if it is needed to use code completion, you don't have to bother to delete the type name later.

## iOS Framework Usage Guidelines

- Do not use `UITableViewController` and `UICollectionViewController`.

- Use RxSwift to subscribe events of UI components.
    - Do not use IBAction.
    - Use `didSet` to create subscriptions, not `viewDidLoad` or other lifecycle callbacks.

- Interface builder(Storyboard/Xib) is just a frontend of AutoLayout, not design tool.
    - Do not use interface builder to configure UI component's properties because:
        - It is hard to review diffs of interface builder's xml.
        - Not every property are unconfigurable on interface builder.

- Do not use "User Defined Runtime Attributes".