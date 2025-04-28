# cs320-project-part-1-solved
**TO GET THIS SOLUTION VISIT:** [CS320 Project Part 1 Solved](https://www.ankitcodinghub.com/product/cs320-fall2023-project-part-1-solved/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;117818&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;2&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (2 votes)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;CS320 Project Part 1 Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (2 votes)    </div>
    </div>
1 Overview

Stack-oriented programming languages utilize one or more stack data structures which the programmer manipulates to perform computations. The specification below lays out the syntax and semantics of such a language which you will need to implement an evaluator for, taking a program and evaluating it into an OCaml value. You must implement a function: interp : string -&gt; string list option

Where the input string is some (possibly ill-formed) stack-language program and the result is a list of things “printed” by the program during its evaluation.

2 Grammar

For part 1, you will need to support the following grammar. The grammar specifies the form of a valid program. Any invalid program, one which is not derivable from the grammar, cannot be given meaning and evaluted. In the case of an invalid program, interp should return None. ⟨prog⟩ is the starting symbol.

2.1 Constants

⟨digit⟩ ::= 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9

⟨nat⟩ ::= ⟨digit⟩ | ⟨digit⟩⟨nat⟩

⟨int⟩ ::= ⟨nat⟩ | -⟨nat⟩

⟨bool⟩ ::= True | False

⟨const⟩ ::= ⟨int⟩ | ⟨bool⟩ | Unit

2.2 Programs

⟨prog⟩ ::= ⟨coms⟩

⟨com⟩ ::= Push ⟨const⟩ | Pop | Trace

| Add | Sub | Mul | Div

| And | Or | Not

| Lt | Gt

⟨coms⟩ ::= ϵ | ⟨com⟩; ⟨coms⟩

Note: ϵ is the empty symbol. We use ϵ to refer to empty strings or empty lists depending on context.

3 Operational Semantics

For part 1, you will need to support the following operational semantics. The operational semantics specifies the meaning of a valid program. For the stack-language, a program is evaluated using a stack and it produces a trace. Once we have fully evaluated the program, we return the resulting trace from interp.

3.1 Configuration of Programs

A program configuration is of the following form.

[S | T ] P

• S: (Stack) stack of intermediate values

• T: (Trace) list of strings logging the program trace

• P: (Program) program commands to be interpreted Examples:

[ϵ | ϵ] PushTrue;Not;Push 1;Lt;ϵ (1)

[1 :: 2 :: ϵ | “True” :: “0” :: ϵ] PushTrue;Push 9;Pop;ϵ (2)

[0 :: True :: ϵ | ϵ] Push 10;Push 9;Add;Trace;ϵ (3)

[True :: False :: 321 :: ϵ | “123” :: “False” :: ϵ] Pop;Pop;Trace;Gt;ϵ (4)

3.2 Program Reduction

The operational semantics of the language is defined in terms of the following single step relation.

[S1 | T1 ] P1 ⇝ [S2 | T2 ] P2

In one step, program configuration [S1 | T1 ] P1 evaluates to [S2 | T2 ] P2. For configurations where P = ϵ, we say that evaluation has terminated as there is no program left to interpret. In this case, return trace T as the final result of your interp function.

3.3 Push

Given any constant c, the command Push c pushes c onto the current stack S. Push never fails.

Push

[S | T ] Push c;P ⇝ [c :: S | T ] P

Examples:

• [1 :: True :: ϵ | “Unit” :: “False” :: ϵ] Push 2;ϵ ⇝ [2 :: 1 :: True :: ϵ | “Unit” :: “False” :: ϵ] ϵ

• [1 :: True :: ϵ | “5” :: ϵ] PushTrue;ϵ ⇝ [True :: 1 :: True :: ϵ | “5” :: ϵ] ϵ

3.4 Pop

c S (constant c is on top of S), the Pop command removes c and leaves the rest of

stack S unmodified.

The Pop command has 1 fail state.

1. PopError: The stack is empty (S = ϵ).

When Pop fails, the string “Panic” is prepended to the trace and the program terminates.

PopStack

[c :: S | T ] Pop;P ⇝ [S | T ] P PopError

[ϵ | T ] Pop;P ⇝ [ϵ | “Panic” :: T ] ϵ

Examples:

• [1 :: True :: ϵ | “Unit” :: “False” :: ϵ] Pop;ϵ ⇝ [True :: ϵ | “Unit” :: “False” :: ϵ] ϵ

• [ϵ | “5” :: ϵ] Pop;Push 12;ϵ ⇝ [ϵ | “Panic” :: “5” :: ϵ] ϵ

3.5 Trace

Given a stack of the form c :: S where c is any valid constant, the Trace command removes c from the stack and puts a Unit constant onto the stack. The string representation of c as determined by the toString function to prepended to the trace.

The Trace command has 1 fail state.

1. TraceError: The stack is empty (S = ϵ).

When Trace fails, the stack is cleared, the string “Panic” is prepended to the trace and the program terminates.

TraceStack

[c :: S | T ] Trace;P ⇝ [Unit :: S | toString(c) :: T ] P TraceError

[ϵ | T ] Trace;P ⇝ [ϵ | “Panic” :: T ] ϵ

The toString function is a special function which you must define to convert constant values into their string representations. The following equations illustrate the strings expected for typical inputs.

toString(123) = “123” (1)

toString(True) = “True” (2)

toString(False) = “False” (3)

toString(Unit) = “Unit” (4)

Examples:

• [1 :: True :: ϵ | “Unit” :: “False” :: ϵ] Trace;ϵ ⇝ [Unit :: True :: ϵ | “1” :: “Unit” :: “False” :: ϵ] ϵ

• [ϵ | “5” :: ϵ] Trace;Push 12;ϵ ⇝ [ϵ | “Panic” :: “5” :: ϵ] ϵ

3.6 Add

Add from the stack and puts their sum (i + j) onto the stack. The Add command has 3 fail states.

1. AddError1: Either i or j is not an integer.

2. AddError2: The stack is empty (S = ϵ).

3. AddError3: The stack has only 1 element (S = c :: ϵ).

When Add fails, the stack is cleared, the string “Panic” is prepended to the trace and the program terminates.

AddStack

i and j are both integers

[i :: j :: S | T ] Add;P ⇝ [(i + j) :: S | T ] P AddError1 i or j is not an integer

[i :: j :: S | T ] Add;P ⇝ [ϵ | “Panic” :: T ] ϵ

AddError2

[ϵ | T ] Add;P ⇝ [ϵ | “Panic” :: T ] ϵ AddError3

[c :: ϵ | T ] Add;P ⇝ [ϵ | “Panic” :: T ] ϵ

Examples:

• [4 :: 5 :: True :: Unit :: ϵ | “False” :: ϵ] Add;ϵ ⇝ [9 :: True :: Unit :: ϵ | “False” :: ϵ] ϵ

• [4 :: True :: Unit :: ϵ | “False” :: ϵ] Add;Trace;ϵ ⇝ [ϵ | “Panic” :: “False” :: ϵ] ϵ

• [4 :: ϵ | “False” :: ϵ] Add;Trace;ϵ ⇝ [ϵ | “Panic” :: “False” :: ϵ] ϵ

3.7 Sub

Given a stack of the form i :: j :: S where both i and j are integer values, the Sub command removes i and j from the stack and puts their difference (i − j) onto the stack. The Sub command has 3 fail states.

1. SubError1: Either i or j is not an integer.

2. SubError2: The stack is empty (S = ϵ).

3. SubError3: The stack has only 1 element (S = c :: ϵ).

When Sub fails, the stack is cleared, the string “Panic” is prepended to the trace and the program terminates.

SubStack

i and j are both integers

[i :: j :: S | T ] Sub;P ⇝ [(i − j) :: S | T ] P SubError1 i or j is not an integer

[i :: j :: S | T ] Sub;P ⇝ [ϵ | “Panic” :: T ] ϵ

SubError2

[ϵ | T ] Sub;P ⇝ [ϵ | “Panic” :: T ] ϵ SubError3

[c :: ϵ | T ] Sub;P ⇝ [ϵ | “Panic” :: T ] ϵ

Examples:

• [4 :: 5 :: True :: Unit :: ϵ | “False” :: ϵ] Sub;ϵ ⇝ [−1 :: True :: Unit :: ϵ | “False” :: ϵ] ϵ

• [4 :: True :: Unit :: ϵ | “False” :: ϵ] Sub;Trace;ϵ ⇝ [ϵ | “Panic” :: “False” :: ϵ] ϵ

• [4 :: ϵ | “False” :: ϵ] Sub;Trace;ϵ ⇝ [ϵ | “Panic” :: “False” :: ϵ] ϵ

3.8 Mul

Mul from the stack and puts their product (i × j) onto the stack. The Mul command has 3 fail states.

• MulError1: Either i or j is not an integer.

• MulError2: The stack is empty (S = ϵ).

• MulError3: The stack has only 1 element (S = c :: ϵ).

When Mul fails, the stack is cleared, the string “Panic” is prepended to the trace and the program terminates.

MulStack

i and j are both integers

[i :: j :: S | T ] Mul;P ⇝ [(i × j) :: S | T ] P MulError1 i or j is not an integer

[i :: j :: S | T ] Mul;P ⇝ [ϵ | “Panic” :: T ] ϵ

MulError2

[ϵ | T ] Mul;P ⇝ [ϵ | “Panic” :: T ] ϵ MulError3

[c :: ϵ | T ] Mul;P ⇝ [ϵ | “Panic” :: T ] ϵ

Examples:

• [4 :: 5 :: True :: Unit :: ϵ | “False” :: ϵ] Mul;ϵ ⇝ [20 :: True :: Unit :: ϵ | “False” :: ϵ] ϵ

• [4 :: True :: Unit :: ϵ | “False” :: ϵ] Mul;Trace;ϵ ⇝ [ϵ | “Panic” :: “False” :: ϵ] ϵ

• [4 :: ϵ | “False” :: ϵ] Mul;Trace;ϵ ⇝ [ϵ | “Panic” :: “False” :: ϵ] ϵ

3.9 Div

Div from the stack and puts their quotient (i ÷ j) onto the stack. The Div command has 4 fail states.

1. DivError0: Both i and j are integers and j = 0.

2. DivError1: Either i or j is not an integer.

3. DivError2: The stack is empty (S = ϵ).

4. DivError3: The stack has only 1 element (S = c :: ϵ).

When Div fails, the stack is cleared, the string “Panic” is prepended to the trace and the program terminates.

DivStack i and j are both integers, j ̸= 0

[i :: j :: S | T ] Div;P ⇝ [(i ÷ j) :: S | T ] P DivError0

i is an integer

[i :: 0 :: S | T ] Div;P ⇝ [ϵ | “Panic” :: T ] ϵ

DivError1 i or j is not an integer

[i :: j :: S | T ] Div;P ⇝ [ϵ | “Panic” :: T ] ϵ DivError2

[ϵ | T ] Div;P ⇝ [ϵ | “Panic” :: T ] ϵ

DivError3

[c :: ϵ | T ] Div;P ⇝ [ϵ | “Panic” :: T ] ϵ Examples:

• [16 :: 8 :: True :: Unit :: ϵ | “False” :: ϵ] Div;ϵ ⇝ [2 :: True :: Unit :: ϵ | “False” :: ϵ] ϵ

• [16 :: 0 :: True :: Unit :: ϵ | “False” :: ϵ] Div;PushUnit;ϵ ⇝ [ϵ | “Panic” :: “False” :: ϵ] ϵ

• [16 :: True :: Unit :: ϵ | “False” :: ϵ] Div;Add;ϵ ⇝ [ϵ | “Panic” :: “False” :: ϵ] ϵ

• [4 :: ϵ | “False” :: ϵ] Div;Trace;ϵ ⇝ [ϵ | “Panic” :: “False” :: ϵ] ϵ

3.10 And

a b a b are boolean values, the And a b

from the stack and puts their conjunction (a ∧ b) onto the stack. The And command has 3 fail states.

1. AndError1: Either a or b is not a boolean.

2. AndError2: The stack is empty (S = ϵ).

3. AndError3: The stack has only 1 element (S = c :: ϵ).

When And fails, the stack is cleared, the string “Panic” is prepended to the trace and the program terminates.

AndStack a and b are both booleans

[a :: b :: S | T ] And;P ⇝ [(a ∧ b) :: S | T ] P AndError1 a or b is not a boolean

[a :: b :: S | T ] And;P ⇝ [ϵ | “Panic” :: T ] ϵ

AndError2

[ϵ | T ] And;P ⇝ [ϵ | “Panic” :: T ] ϵ AndError3

[c :: ϵ | T ] And;P ⇝ [ϵ | “Panic” :: T ] ϵ

Examples:

• [True :: True :: Unit :: ϵ | “False” :: ϵ] And;ϵ ⇝ [True :: Unit :: ϵ | “False” :: ϵ] ϵ

• [False :: True :: Unit :: ϵ | “False” :: ϵ] And;Trace;ϵ ⇝ [False :: Unit :: ϵ | “False” :: ϵ] Trace;ϵ • [True :: 4 :: Unit :: ϵ | “False” :: ϵ] And;Pop;ϵ ⇝ [ϵ | “Panic” :: “False” :: ϵ] ϵ

3.11 Or

Given a stack of the form a :: b :: S where both a and b are boolean values, the Or command removes a and b from the stack and puts their disjunction (a ∨ b) onto the stack. The Or command has 3 fail states.

1. OrError1: Either a or b is not a boolean.

2. OrError2: The stack is empty (S = ϵ).

3. OrError3: The stack has only 1 element (S = c :: ϵ).

When Or fails, the stack is cleared, the string “Panic” is prepended to the trace and the program terminates.

OrStack

a and b are both booleans

[a :: b :: S | T ] Or;P ⇝ [(a ∨ b) :: S | T ] P OrError1 a or b is not a boolean

[a :: b :: S | T ] Or;P ⇝ [ϵ | “Panic” :: T ] ϵ

OrError2

[ϵ | T ] Or;P ⇝ [ϵ | “Panic” :: T ] ϵ OrError3

[c :: ϵ | T ] Or;P ⇝ [ϵ | “Panic” :: T ] ϵ

Examples:

• [True :: True :: Unit :: ϵ | “False” :: ϵ] Or;ϵ ⇝ [True :: Unit :: ϵ | “False” :: ϵ] ϵ

• [False :: True :: Unit :: ϵ | “False” :: ϵ] Or;Trace;ϵ ⇝ [True :: Unit :: ϵ | “False” :: ϵ] Trace;ϵ

• [True :: 4 :: Unit :: ϵ | “False” :: ϵ] Or;Pop;ϵ ⇝ [ϵ | “Panic” :: “False” :: ϵ] ϵ

3.12 Not

a S where a is a boolean values, the Not command removes a from the stack and

puts its negation (¬a) onto the stack.

The Not command has 2 fail states. 1. NotError1: a is not a boolean.

2. NotError2: The stack is empty (S = ϵ).

When Not fails, the stack is cleared, the string “Panic” is prepended to the trace and the program terminates.

NotStack NotError1

a is a boolean a is not a boolean

[a :: S | T ] Not;P ⇝ [(¬a) :: S | T ] P [a :: S | T ] Not;P ⇝ [ϵ | “Panic” :: T ] ϵ

NotError2

[ϵ | T ] Not;P ⇝ [ϵ | “Panic” :: T ] ϵ Examples:

• [True :: Unit :: ϵ | “False” :: ϵ] Not;ϵ ⇝ [False :: Unit :: ϵ | “False” :: ϵ] ϵ

• [4 :: Unit :: ϵ | “False” :: ϵ] Not;Pop;ϵ ⇝ [ϵ | “Panic” :: “False” :: ϵ] ϵ

• [ϵ | “False” :: ϵ] Not;Add;ϵ ⇝ [ϵ | “Panic” :: “False” :: ϵ] ϵ

3.13 Lt

Given a stack of the form i :: j :: S where both i and j are integer values, the Lt command removes i and j from the stack and puts the boolean result of their comparison (i &lt; j) onto the stack. The Lt command has 3 fail states.

1. LtError1: Either i or j is not an integer.

2. LtError2: The stack is empty (S = ϵ).

3. LtError3: The stack has only 1 element (S = c :: ϵ).

When Lt fails, the stack is cleared, the string “Panic” is prepended to the trace and the program terminates.

LtStack

i and j are both integers

[i :: j :: S | T ] Lt;P ⇝ [(i &lt; j) :: S | T ] P LtError1 i or j is not an integer

[i :: j :: S | T ] Lt;P ⇝ [ϵ | “Panic” :: T ] ϵ

LtError2

[ϵ | T ] Lt;P ⇝ [ϵ | “Panic” :: T ] ϵ LtError3

[c :: ϵ | T ] Lt;P ⇝ [ϵ | “Panic” :: T ] ϵ

Examples:

• [4 :: 5 :: True :: Unit :: ϵ | “False” :: ϵ] Lt;ϵ ⇝ [True :: True :: Unit :: ϵ | “False” :: ϵ] ϵ

• [5 :: 5 :: True :: Unit :: ϵ | “False” :: ϵ] Lt;ϵ ⇝ [False :: True :: Unit :: ϵ | “False” :: ϵ] ϵ

• [4 :: True :: Unit :: ϵ | “False” :: ϵ] Lt;Trace;ϵ ⇝ [ϵ | “Panic” :: “False” :: ϵ] ϵ

3.14 Gt

i j :: S where both i and j are integer values, the Gt command removes i and j

from the stack and puts the boolean result of their comparison (i &gt; j) onto the stack. The Gt command has 3 fail states.

1. GtError1: Either i or j is not an integer.

2. GtError2: The stack is empty (S = ϵ).

3. GtError3: The stack has only 1 element (S = c :: ϵ).

When Gt fails, the stack is cleared, the string “Panic” is prepended to the trace and the program terminates.

GtStack

i and j are both integers

[i :: j :: S | T ] Gt;P ⇝ [(i &gt; j) :: S | T ] P GtError1 i or j is not an integer

[i :: j :: S | T ] Gt;P ⇝ [ϵ | “Panic” :: T ] ϵ

GtError2

[ϵ | T ] Gt;P ⇝ [ϵ | “Panic” :: T ] ϵ GtError3

[c :: ϵ | T ] Gt;P ⇝ [ϵ | “Panic” :: T ] ϵ

Examples:

• [4 :: 5 :: True :: Unit :: ϵ | “False” :: ϵ] Gt;ϵ ⇝ [False :: True :: Unit :: ϵ | “False” :: ϵ] ϵ

• [10 :: 5 :: True :: Unit :: ϵ | “False” :: ϵ] Gt;ϵ ⇝ [True :: True :: Unit :: ϵ | “False” :: ϵ] ϵ

• [5 :: 5 :: True :: Unit :: ϵ | “False” :: ϵ] Gt;ϵ ⇝ [False :: True :: Unit :: ϵ | “False” :: ϵ] ϵ

• [4 :: True :: Unit :: ϵ | “False” :: ϵ] Gt;Trace;ϵ ⇝ [ϵ | “Panic” :: “False” :: ϵ] ϵ

4 Full Examples

• Compute the polynomial x2 − 4x + 7 at 3:

Push 3;

Push 3;

Mul;

Push -4;

Push 3;

Mul;

Add;

Push 7;

Add;

Trace;

Result: Some [“4”]

• De Morgan’s Law:

Push False;

Push False;

And;

Not;

Trace;

Push False;

Not;

Push False;

Not;

Or;

Trace;

Result: Some [“True”; “True”]

• x2 is monotonic:

Push 2;

Push 2;

Mul;

Push 3;

Push 3;

Mul;

Gt;

Trace;

Result: Some [“True”]
