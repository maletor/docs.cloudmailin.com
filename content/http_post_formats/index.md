---
title: Receiving Your Email as an HTTP POST - Formats
---

# Receiving Your Email as an HTTP POST

CloudMailin sends your email as an HTTP POST to the URL that you specify. There are several formats to choose from:

| Format        | Details                                 | Description                                                               |
|-------------------------------------------------------------------------------------------------------------------------------------|
| `Original`    | [details](/http_post_formats/original/)  | The original CloudMailin message format. This is stable and battle hardened. It's currently the default format. |
| `JSON`        | [details](/http_post_formats/json/)      | A new `JSON` based format consisting of four main parts `envelope`, `headers`, `body`, `attachments`. |
| `Multipart`   | [details](/http_post_formats/multipart/) | Exactly the same as the `JSON` format but this uses `multipart/form-data` to encode the details. |
| `Raw Message` | [details](/http_post_formats/raw/)       | This sends just original Raw message as a single `multipart/form-data` request parameter. |

If you have an existing app using CloudMailin then continuing to make use of the [Original Format](/http_post_formats/original/) makes sense. If you're starting a fresh app then their the [Multipart](/http_post_formats/multipart/) or [JSON](/http_post_formats/json/) formats will be useful depending on whether you prefer to work with JSON or not.

If you just want to use CloudMailin to forward the entire email to your website over http without parsing or processing it at all then the [Raw format](/http_post_formats/raw/) does exactly that.

## Testing a Format

If you want to see how a format will look with your own content we recommend using the [WebhookApp](http://webhookapp.com). Simply set the [WebhookApp](http://webhookapp.com) as your message url target and then send an email. The message content will then be sent over HTTP to the app using WebSockets so you can view this content and try out the format.