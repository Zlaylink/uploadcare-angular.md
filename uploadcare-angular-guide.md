# File Uploader for Angular
Looking for a dead-simple way to integrate image uploading/cropping with your [Angular](https://angular.io/) project? Then look no further! Uploadcare provides a fantastic [widget](https://uploadcare.com/features/widget/) for uploading images from multiple sources. Combine this with the power of Angular and you've got yourself an image uploading solution that's far better than most other offerings.

In this tutorial, we are going to cover the process of building and running a simple Angular app and integration the Uploadcare widget into it. 

## [](#make-uc-account)Step 1\. Create Uploadcare user account

Feel free to skip the step if you’ve already got an Uploadcare account. Otherwise, here’s how you make one:

*   Go to our [signup page](https://uploadcare.com/accounts/signup/)
*   Provide us with your email and choose a password
*   Confirm your email by clicking your validation link

## [](#get-key)Step 2\. Grab a public key for your project

You will need to define an Uploadcare public API key in the File Uploader settings to set a project your files will go to. So, navigate to your dashboard and discover a public key for [one of your projects](https://community.uploadcare.com/t/what-is-a-public-and-private-key-and-where-do-i-find-them/30?utm_source=uploadcare.com&utm_medium=uploadcare&utm_campaign=docs_guides_jotform).

## [](#make-form)Step 3\. Build an Angular app and add the uploader

The step is about building an app itself. Please look through the [quickstart](https://angular.io/guide/quickstart) and navigate to their [main page](https://angular.io/) to click “Get started.”

### Install the Angular CLI

To install the CLI using npm, open a terminal/console window and enter the following command:

``` npm install -g @angular/cli ```

### Create a workspace and initial application

To create a new workspace and initial app project:

1. Run the CLI command ng new and provide the name my-app, as shown here:
 ``` ng new my-app ```
2. The ng new command prompts you for information about features to include in the initial app project. Accept the defaults by pressing the Enter or Return key.

### Serve the application

Angular includes a server, so that you can easily build and serve your app locally.
1. Go to the workspace folder (my-app).
2. Install ngx-uploadcare-widget
2. Launch the server by using the CLI command ng serve, with the --open option.
```cd my-app```
```npm install ngx-uploadcare-widget```
```ng serve --open```

The ng serve command launches the server, watches your files, and rebuilds the app as you make changes to those files.
The --open (or just -o) option automatically opens your browser to http://localhost:4200/.
Your app greets you with a message:
![](https://ucarecdn.com/1bc110e9-0ec8-405d-ad15-6384866db8de/-/preview/1162x693/-/setfill/ffffff/-/format/jpeg/-/progressive/yes/)

## [](#Integrate-widget)Step 4\. Integrating Uploadcare widget into an Angular app

### Import the module in module.ts
```javascript
import { UcWidgetModule } from 'ngx-uploadcare-widget'; 
```

### Import the module to yours
```
@NgModule({
  imports: [
    ...,
    UcWidgetModule,
  ],
  ...
})
...
```

### Use the component in your template
```html
<!-- with default markup -->
<ngx-uploadcare-widget
  images-only="true"
  public-key="YOUR_PUBLIC_KEY">
</ngx-uploadcare-widget>

<!-- without any markup -->
<ngx-uploadcare-widget-custom
  images-only="true"
  public-key="YOUR_PUBLIC_KEY">
</ngx-uploadcare-widget-custom>
```

### Have fun with the widget events
The component currently supports three widget events:

* `on-change`
* `on-upload-complete`
* `on-progress`

Here is how you can handle those three,

```html
<ngx-uploadcare-widget
  images-only="true"
  public-key="demopublickey"
  (on-upload-complete)="yourOnUploadHandler($event)"
  (on-change)="yourOnChangeHandler($event)"
  (on-progress)="yourOnProgressHandler($event)">
</ngx-uploadcare-widget>
```
You can learn more about this widget events in our [docs](https://uploadcare.com/docs/api_reference/javascript/widget/?utm_source=github&utm_campaign=ngx-uploadcare-widget#widget-on-change).

## [](#run)Step 5\. Run the app and test it

![](https://ucarecdn.com/9af4a378-c037-4a6d-931f-aa880d1077c5/-/preview/1162x693/-/setfill/ffffff/-/format/jpeg/-/progressive/yes/)

That’s it. We have just created an Angular app with file uploads in 5 simple steps. If you have any questions, consider posting those in our [Community Area](https://community.uploadcare.com/?utm_source=uploadcare.com&utm_medium=uploadcare&utm_campaign=docs_guides_jotform).

## Questions?

We’re always happy to help with code, integration, and other stuff. [Search](#search-docs) our site for more info or post your question in our [Community Area](https://community.uploadcare.com/).
