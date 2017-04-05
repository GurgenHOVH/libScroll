# libScroll 3.0 beta

LibScroll is the Livecode library, which makes it easy to connect native scrolling to groups.
The main feature of this library is the use of one native scroller for the whole stack. 
This means that the program creates one native element, and then only changes its properties if necessary.

## Installation

Add the library to your project.
start using stack "libScroll".
libScrollInit.

## Settings

On the top of library you will see the settings section
1. constant kScrollerName = "libScrollNative"
2. constant kSendCallbacks = false
3. constant kHIndicator= false
4. constant kVIndicator= false

1. kScrollerName is the native scroller name, change if necessary.
2. kSendCallbacks: set true if want to get callbacks from library.
3. kHIndicator: set to true if you want make the horizontal scrollbar enable.
3. kVIndicator: set to true if you want make the vertial scrollbar enable.

## Callbacks

1. libScrollCreated: sent to the main stack when scroller is crated(not enabled! Just created).
2. libScrollEnabled: sent to scrolling group when the scrolling is enabled and ready to scroll.
3. libScrollDisabled: sent to scrolling group when the scrolling is disabled.
4. libScrollDeleted: sent to main stack when scroller is deleted(to use the library again to neeed to call libScrollInit again).
5. libScrollDidScroll: sent to scrolling group when the scroller is doing scroll. The two parameters with callback is the hScroll size and vScroll size.
6. libScrollStartDrag: sent to scrolling group when the scroller start drag.
7. libScrollEndDrag: sent to scrolling group when the scroller end drag.

# Usage

## libScrollEnable

To enable scrolling you need to call libScrollEnable handler

-- PARAMETERS
--   pGroupID: the long id of scrolling group
--   pReset: true/false. If true the library will reconnect the group if already connected
--   pDirection: horizontal/vertical. The direction to enable scrolling. If empty then will scroll for both directions

Example: 
libScrollEnable the long id of group "myGroupToScroll", false, "vertical"
libScrollEnable the long id of group "myHorizontalGroup", true, "horizontal"

---------------------------------------------------------------------------------------------------

## libScrollDisable
To disable scrolling you need to call libScrollDisable handler
-- PARAMETERS
--     none

Example:
libScrollDisable

---------------------------------------------------------------------------------------------------

## libScrollSetHScroll
To manualy set the horizontal scroll size of scroller call libScrollSetHScroll handler.
-- PARAMETERS
--         pValue: Integer. The value to set to native scroller

Example:
libScrollSetHScroll 150
libScrollSetHScroll hScrollSize

---------------------------------------------------------------------------------------------------

## libScrollSetVScroll
To manualy set the vertical scroll size of scroller call libScrollSetVScroll handler.
-- PARAMETERS
--         pValue: Integer. The value to set to native scroller

Example:
libScrollSetVScroll 150
libScrollSetVScroll vScrollSize

---------------------------------------------------------------------------------------------------

## libScrollDelete
To delete the native scroller and disable the linrary call libScrollDelete

---------------------------------------------------------------------------------------------------

### Gurgen Hovhannistan
### g.hovhannisyan@digitalpomegranate.com
### DIGITAL POMEGRANATE LLC
### 2017