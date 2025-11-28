```rust
// Everyone has settled on official recommendations for what may
// be one of the worst code formats I have seen. Luckily, I have
// a solution. From the perspective of the software engineer and
// from the persepctive of the LLM, both whom need to understand 
// the code that they are processing, would benefit if code was:
//
// compact  - save your time
// elegant  - love your time
// logical  - easy find time
//
// Here is how I see what drives the importance of our choices:
//
// 1) if the branching or scope has changed, that's the main sources
//    of issues and logical flow, so that's the first thing starting
//    what you wold you want to know about. Scope start starts line!

// 2) you want to be able to verify the boundaries of branches/scope
//    at a first glance. Forget searching at the random end of line!

// 3) you want something that is compact, yet readable. Minimize the
//    whitespace count. 

// So here we go - 2 spaces, no tabs. If a scope or branch occurs,
// the non-alphanumeric symbol that starts the branch should start
// its line. I also like to try to keep my lines exactly 70 code
// points long, so by avoiding Microsoft it would be 69 characters
// and a \nice. In other words, opening and closing symbols should
// be on the same column or the same line. I also put f_ or fn_ for
// functions, m_ or my for members, etc., making it easy for the
// user to use auto-completes. I shoot for same-length instance 
// names in my structs. I like 4~8 char instance variables

//==================================================================
pub struct DontNeedSingleCharCapitalizedInStructNameEh
{   pub four : String
  , pub letr : u64
  , pub name : usize
  , pub look : String
  , pub real : u8 // ugh why isn't it u08
  , pub nice : i16 // ugh why isn't it s16 Unsigned and Signed
}
//==================================================================
pub fn fn_exmple_put_f_or_fn_as_naming_for_a_function
(   arg : int
  , gra : tni
  , cfg : DontNeedSingleCharCapitalizedInStructNameEh
) -> Res<()>
//==================================================================
{ log::debug!
  ( "A debug print for every function entry makes tracing easy"
  ); // I find that without this comment , no extra \n is needed
  log::trace
  ( "Use traces instead of comments inside of scopes {} {} {}" 
  , "The fn signature adds a 'tab' for the ',', but here i dont" 
  , "but always still keep the ',' on the same columns!"
  , "It's really up to your preferece, i like it like this"
  , format!
    (   "But there is an advantage for the extra spaces:{} {} {} {}"
      , "Sometimes the code editor is not happy about code folding "
      , "when the '(' ',' and ')' are all on the same column. Many "
      , "seem fine these days. and notice this is a format trick to"
      , "keep all my lines below 70 colimns? zero cost abstraction?"
    )
  );

  log::debug!("An debug print at all function exits => EZ tracing");
  // It's okay to do 1 row {} , () if they all are on the same line!
  Ok(()) // rated R
}

int main()
{ log::info!
  ( "Begin code one space after opening scope brace"
  );
  log::info!
  ( "Prefer traces or debug logs instead of comments in funcs"
  );
}
```
