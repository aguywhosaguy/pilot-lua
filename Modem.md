A part which can be used to universally and publicly store data on a "domain" and communicate between regions.

## Table of contents

### Methods
* [`void Modem:PostRequest(string domain, string data)`](#void-modempostrequeststring-domain-string-data)
* [`string Modem:GetRequest(string domain)`](#string-modemgetrequeststring-domain)
* [`void Modem:SendMessage(string data, int id)`](#void-modemsendmessagestring-data-int-id)

### Events
* [`Event Modem.MessageSent(string data)`](#event-modemmessagesentstring-data)

___

## `void Modem:PostRequest(string domain, string data)`

> Posts the `data` onto the `domain` in the WOS internet. Lock your microcontroller to protect the data from being edited by other players.
> This can't be used to access the web.

___

## `string Modem:GetRequest(string domain)`

> Gets the data listed on the given `domain` in the WOS internet.
> This can't be used to access the web.

___

## `void Modem:SendMessage(string data, int id)`

> Sends the given `data` cross region to all modems with the [NetworkId](#) `id`.

___

## `Event Modem.MessageSent(string data)`

> Fired when the Modem receives a message from another modem.
