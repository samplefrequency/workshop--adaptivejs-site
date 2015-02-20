#Step 1: Generate a View

In addition to generating a new project, the Adaptive.js Generator has a sub-generator that sets up a new view for your project. The sub-generator creates:
* a view file,
* the dust template,
* a view-script file, and
* a view test file.


##Task

###Create a New 'category' View 

1. In your `workshop--adaptivejs-site` project folder, enter the following command to run the sub-generator with Yeoman:

    ```
    yo adaptivejs:view
    ```

2. When the generator prompts you for a name, enter `category`.
3. Enter `base` as the view to extend.

    ![View Generator](https://s3.amazonaws.com/uploads.hipchat.com/15359/64553/VXQhsUYEz8Jjnqj/Screen%20Shot%202015-01-15%20at%205.05.49%20PM.png)

4. Add the view to the router file. Navigate to your project folder in Finder. Locate the `adaptation` folder. Open the file `router.js` with an editor app.
5. Add the path for the new view file to the dependecies array.
6. List the view `Category` as an argument in corresponding function definition:


    ![Add View to Router](https://s3.amazonaws.com/uploads.hipchat.com/15359/64553/6ShtDgoKJvxKuCq/Screen%20Shot%202015-02-05%20at%201.15.29%20PM.png)

7. Remove the generated calls to `router.add()` and replace them with the following:

    ```javascript
    router
        .add(Router.selectorMatch('body.home'), Home)
        .add(Router.selectorMatch('body.category'), Category);
    ```


    The `.add()` function creates a new route that loads the given view upon the return of a Boolean value from the function. The `Router.selectorMatch()` function returns true when an element that matches the selector exists on the current page.

8. Back in the Terminal, enter the `grunt preview` command to start the browser preview.
9. Work through the third section, [Preview the Adaptive.js Site](https://cloud.mobify.com/docs/adaptivejs/getting-started/new-project/#/start-adaptivejs-server) of the Getting Started (New Project) guide.
    Use the `http://www.merlinspotions.com/potions` URL for the site.

    A page that is similar to the Merlin's Potions homepage appears but but with content from the category page included under the header.

10. To stop the preview, enter `[control] c` on the command line.

##Continue to Step 2

When you're ready to continue to Step 2, run the following command:

```
git reset --hard HEAD && git clean -df && git checkout step-2-populate-category-page
```

Then, follow the directions in the  [README](https://github.com/mobify/workshop--adaptivejs-site/blob/step-2-populate-category-page/README.md) for the Step 2 branch.
