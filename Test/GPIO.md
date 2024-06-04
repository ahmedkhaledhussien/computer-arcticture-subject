|Port|Usage|
|:---|:----|
|**GPIOHBCTL**| Enable/Disable High Performance (0 -> APB mode, 1 -> AHB mode)|
|**RCGC2**| controls the clock gating logic in normal Run mode (1 means module receives clock and functions, 0 means disabled [saves power])|
|**RCGCGPIO**| Enable/Disable given Port (1 means port enabled 0 means port disable)|
|**GPIODIR**| Configure pin IO (1 means output, 0 means input)|
|**GPIOAFSEL**| mode control select register (0 means Pin is GPIO, 1 Pin is controlled by an associated peripheral [alternate function]) GPIOPCTL is used to select on of the functions|
|**GPIODATA**|the data register, In software control mode, values written in the GPIODATA register are transferred onto the GPIO port pins if the respective pins have been configured as outputs through the GPIO Direction (GPIODIR) register|
|**GPIOPUR**|pull-up control register. When a bit is set, a weak pull-up resistor on the corresponding GPIO signal is enabled.|
|**GPIODEN**|digital enable register. |
|**GPIOLOCK**|enables write access to the GPIOCR register. Writing 0x4C4F.434B to the GPIOLOCK register unlocks the GPIOCR register. (when write accesses are disabled, or locked, reading the GPIOLOCK register returns 0x0000.0001. When write accesses are enabled, or unlocked, reading the GPIOLOCK register returns 0x0000.0000.)|
|**GPIOCR**|commit register. The value of the GPIOCR register determines which bits of the GPIOAFSEL, GPIOPUR, GPIOPDR, and GPIODEN registers are committed when a write to these registers is performed. (0 means data written to those registers can not commit, 1 means data commited and new values reflected, and this is only if the GPIOLOCK is unlocked)|
|**GPIOAMSEL**|Analog Mode Select. This register is only valid for ports and pins that can be used as ADC AINx inputs. If any pin is to be used as an ADC input, the appropriate bit in GPIOAMSEL must be set to disable the analog isolation circuit.|
