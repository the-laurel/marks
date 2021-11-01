# Marks Factory Kitchen Sink v1

There are two types of React components that can be used:
- simple html directive, extended to Marks Factory provided components
- complex components, based on taylor. Taylor core language :Link[playground]{src="https://observablehq.com/@loredanacirstea/hello-taylor"}. Marks factory uses a React extension for taylor, allowing you to build more complex UIs.

Enter edit mode to view the mark source.

::a[]{id="basecomponents"}
## Base Components

### Text

::span[Some text with ::span]{}
::Span[Some text with ::Span]{}
::Text[Some text with ::Text]{}
<uniqueid1:(react-text {} "Some text with react-text")>

### Input

::Input[]{label="input1" placeholder="input placeholder"}
::br[]{}
::br[]{}
::Textarea[]{label="textarea1" width="100%" rows=4 placeholder="textarea placeholder"}

<uniqueid2:(react-div {"style" {"display" "flex" "paddingTop" "10px"}} (list
    (react-input {"placeholder" "react-input placeholder" "style" {"marginRight" "10px" "height" "20px"} } )
    (react-textarea {"placeholder" "react-textarea placeholder"} )
))>

### Images & Videos

::Image[]{src="/menu/tikkun.svg" alt="image" width=35}
::br[]{}
::Video[]{src="https://www.youtube.com/embed/NoL_n9bzEn0" width="300px" height="200px"}

### Button

::Button[a button]{}

::Text[Result: @v]{label="result1"}
::Input[]{label="inputA" placeholder="a string"}

<uniqueid4:(react-div {} (list
    (react-input {
        "key" 1
        "placeholder" "a string"
        "onChange" (fn* (val) (set-state "inputB" val))
        "style" {"marginLeft" "20px"}
    })
    (react-button {
        "key" 2
        "onClick" (fn* ()
            (set-state "result1" (str (get-state "inputA") (get-state "inputB") ))
            )
    } "react-button")
))>

### Link

https://twitter.com/tikkun_olam_app - opens in the same window
:Link[Twitter Link]{src="https://twitter.com/tikkun_olam_app"} - opens in a new window

<reactLink1:(react-link {
 "src" (str "https://twitter.com/" "tikkun_olam_app")
} "Twitter react-link" )>

### Select

"addresses" is a value provided by Marks Factory
:Select[]{options=addresses label=selectedContract trigger=onChange}

::DateRange[]{label="datevalue"}

### Spacing

::br[]{}

### Formulas

:Math[\text{\\(\frac {3} {4}\\)}]{}

### Editor

::Editor[]{value="# Description" label="description" height=100}
::Markdown[]{label="description" value="# Description"}

### Tree Select

::TreeSelect[]{placeholder="Select infraction..." label="tags" data="DEFAULT_TAGS" minWidth="200px" width="100%"}

### Map

::Map[]{height="200px" width="200px" label="coordinates" zoom=4}

### Tabs

<tabExample:(react-div {} (list
	(react-tabs {"defaultActiveKey" "1" "key" 1} (list
                  (react-tabpane {"tab" "tab1" "key" "1" "style" {}}
                  (react-text {} "tab1")
                  )
                   (react-tabpane {"tab" "tab2" "key" "2" "style" {}}
                  (react-text {} "tab2")
                  )
    ))
))>

::a[]{id="reactcomponents"}
## Create React components

You can write React components that interact with one another. In the above example, try changing the selected value and you will see the text input change as well.

::Input[]{label="externalValue"}

<BComponent:((fn* (props)
(let* (
  inputState "ola"
  setExternalState (set-state "externalValue" inputState)
  render (fn* (props state stateChangers)
    (let* (
        inputSetter (fn* (v)
        (do
            ((get stateChangers "inputState") v)
                (set-state "externalValue" v)
            )
        )
      )
      (react-div {} (list
        (react-input {
          "key" 1
          "placeholder" "hello"
          "value" (get state "inputState")
          "onChange" inputSetter
        })
        (react-select {
          "key" 2
          "options" [{"label" "hello" "value" "hello"} {"label" "ola" "value" "ola"}]
          "value" (get state "inputState")
          "onChange" inputSetter
        })
      ))
    )
  )
)
  (react props {"inputState" inputState} {"render" render})
)
) {})
>

::a[]{id="watchforchange"}
## Watch for global variable change in taylor components

::Input[]{label="inputValue10"}

<watchForChange:(watch
  ["inputValue10"]
    (fn* ()
    (react-text {} (get-state "inputValue10"))
    )
)>

::a[]{id="envdata"}
## Setting data in the environment

<componentid1:(def! selectOptions ["option1" "option2" "option3"])>

<aselectComponent:(react-select {
  "key" 1
  "options" selectOptions
})>

::a[]{id="stylechanges"}
## Style

<astylecomponent:(set-style {
      "mauve" {
        "color" "#6d45a0"
      }}
)>

<astyledcomponent:(react-text {"className" "mauve"} "Some colored text")>

:::center
Centered
:::


