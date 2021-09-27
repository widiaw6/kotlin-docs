# Code Structure

## Class layout

The contents of a class should go in following order:
1. Property declarations
2. `init` blocks
3. Secondary constructor, if does exist
4. Overridden methods & interface implementation (keep the implementing members in the same order)
5. Class methods
6. `companion object`

```kotlin
class LoginFragment : BaseFragment {

    // 1. Property declarations
    private val viewModel by viewModels<LoginViewModel>()

    // 2. Initializer block
    init {
        contentRes = R.layout.fragment_login
        toolbarTitle = R.string.text_login_with
    }

    // 3. Secondary constructor

    // 4. Overridden methods
    override fun onViewCreated(view: View, savedInstanceState: Bundle?) {
        super.onViewCreated(view, savedInstanceState)
    }

    // 5. Class methods
    fun fetchMyLocationWithPermissionCheck() { }

    // 6. Companion object
    companion object { }
}
```