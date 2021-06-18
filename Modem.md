A part which can be used to universally and publicly store data on a "domain" and communicate between regions.

## Table of contents
* [`void Modem:PostRequest(string domain, string data)`](#void-modempostrequeststring-domain-string-data)
* [`string Modem:GetRequest(string domain)`](#string-modemgetrequeststring-domain)
* [`void Modem:SendMessage(string data, int id)`](#void-modemsendmessagestring-data-int-id)

___

## `void Modem:PostRequest(string domain, string data)`

> Posts the `data` onto the `domain`. Lock your microcontroller to protect the data from being edited by other players.
> This does not emit an HTTP request or access the web.

___

## `string Modem:GetRequest(string domain)`

> Gets the data listed on the given `domain`.
> This does not emit an HTTP request or access the web.

___

## `void Modem:SendMessage(string data, int id)`

> Sends the given `data` cross region to all modems with the id `id`.