#recursion #programming #cpp 

Like all other functions, the recursive function’s data is stored in the stack memory in the form of a stack frame. This stack frame is deleted once the function returns some value. In recursion,

> - The function call is made before returning the value, so the stack frame for the progressive recursive calls is stored on top of existing stack frames in the stack memory.
> - When the topmost function copy returns some value, its stack frame is destroyed and the control comes to the function just before that particular copy after the point where the recursive call was made for the top copy.
> - The compiler maintains an instruction pointer to track where to return after the function execution.

