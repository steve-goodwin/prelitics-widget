# Prelitics Javascript Widget Integration

Prelitics has been designed to be developer friendly, with minimal integration time and without taking over your website with loads of Javascript code.

## Installing Our Tracking Widget

Our tracking widget enables us to capture data in order to:

 - Log visitor data
 - Log sales data
 - Log product data
 - Build product recommendations

You will need to place this code into the <head> of your document, this will install all of the javascript you will need to insert onto your site in order for Prelitics to function.
 
```javascript
<script src="http://js.prelitics.com/2/widget.js" id="prelitics-js" data-api-key="[YOUR_API_KEY_HERE]"></script>
```

#Click Tracking

Click tracking has a number of components in order to help collect and monitor what's being clicked on your website and also how users are browsing your website.

### Click Tracking

Click tracking enables you to track when your product links are clicked by an end user. To install click tracking you will be required to add the following data attributes to your HTML markup:

```html
<a href="#" data-prelitics-track-action="click-tracking" data-prelitics-track-name="[PRODUCT_NAME]" data-prelitics-track-id="[PRODUCT_ID]">View Product</a>
```

### Add To Basket Click Tracking

Add to basket click tracking allows Prelitics to capture and log what products are being added to users baskets. To add Add to basket tracking to your links you will need to add the following data attributes to you "Add To Basket" links:

```html
<a href="#" data-prelitics-track-action="add-to-basket-tracking" data-prelitics-track-id="[PRODUCT_ID]" data-prelitics-track-name="[OPTIONAL_PRODUCT_TITLE]">Add To Basket</a>
```

### Remove From Basket Click Tracking

If you are using the add to basket click tracking then its just as important to implement the Remove from basket click tracking. If you do not implement this your sales figures in your Prelitics dashboard will be skewed. To implement the Remove from basket click tracking please add the following data attributes to your "Remove From Basket" links:

```html
<a href="#" data-prelitics-track-action="remove-from-basket-tracking" data-prelitics-track-id="[PRODUCT_ID]">Remove</a>
```

# Logging

Logging enables you to add markup to use the Prelitics log functionality.

### Item View Logging

Item logging enables Prelitics to log product item views, by doing this we can build up an overview of product data when we run our nightly analysis. To add item view logging you will need to add the following to your <body> markup (you can also add these data attributes to any html tag e.g. <span>, <div> etc...):

```html
<body data-prelitics-track-action="item-view" data-prelitics-track-id="[PRODUCT_ID]" data-prelitics-track-name="[OPTIONAL_PRODUCT_TITLE]">
```

### Checkout Complete Logging

If you are using the "Add To Basket" & "Remove From Basket" click tracking then you should add also use our "Checkout Complete Logging" method. The add to basket and remove from basket methods build up a basket with Prelitics, this can only be logged as a qualified sale once the "Checkout Complete Logging" method is called. This method needs to be added to the last page in your checkout (normally the payment complete page) in order to qualify the sale and not give you any data errors whilst Prelitics is analysing logged data. To add checkout complete logging you will need to add the following to your <body> markup (you can also add these data attributes to any html tag e.g. <span>, <div> etc...): 

```html
<body data-prelitics-track-action="basket-tracking">
```

# Recommendation Widget

The recommendation widget provides a visual display to your Users by adding a HTML div to your markup. To add the widget to your site you will need to add a minimum of the following code to your website:

```html
<div data-prelitics-widget="recommendation"></div>
```

This will place a recommendation widget on your page with our default settings. The other settings through data attributes available to you are:

#### Name Visible

This makes the name visible or invisible (true by default).

```html
data-prelitics-widget-item-name-visible="true|false"
```

#### Image Visible

This makes the image visible or invisible (true by default).

```html
data-prelitics-widget-item-image-visible="true"
```

#### Price Visible

This makes the price visible or invisible (false by default).

```html
data-prelitics-widget-item-price-visible="true|false"
```

#### Limit Results

This attribute limits the number of results returned by the widget.

```html
data-prelitics-widget-item-limit="[LIMIT]"
```

#### Layout Class

This attribute allows you to control the styling of recommendation widgets for vertical or horizontal layout. A 'vertical" or "horizontal" class is added to the main Prelitics widget div (this is set to horizontal by default):

```html
data-prelitics-widget-layout="vertical|horizontal"
```

#### Widget Title

If you wish to add a title to the inside of your recommendation widget then you will need to add the following data attribute. This will add your title text using a <h2>

```html
data-prelitics-widget-title="[TITLE_HERE]"
```

## Widget Styling

Prelitics is totally customisable and uses only HTML markup, we have added namespaced classes to all HTML tags so not to clash with any existing styles you have on your website. The following code shows all classes and allows you to fully customise the widgets styling, the base styling is shown below:

```css
<style>
        .preliticsWidget { border: 1px solid #CCC; font-size: 12px; }
        .preliticsWidget h2.preliticsWidgetTitle { margin: 0; padding: 15px; background-color: #CCC; font-weight: bold; color: #666; }
        .preliticsWidget ul.preliticsWidgetList { margin: 0; padding: 15px; }
        .preliticsWidget ul.preliticsWidgetList li.preliticsWidgetListItem { margin: 0; padding: 0; list-style-type: none; width: 20%; display: inline-block; overflow: hidden; }
        .preliticsWidget ul.preliticsWidgetList li.preliticsWidgetListItem a.preliticsWidgetListItemLink { display: block; text-align: center; text-decoration: none; }
        .preliticsWidget ul.preliticsWidgetList li.preliticsWidgetListItem a.preliticsWidgetListItemLink:hover { }
        /*.preliticsWidget ul.preliticsWidgetList li.preliticsWidgetListItem a.preliticsWidgetListItemLink img { width: 100%; max-width: 150px; max-height: 150px; }*/
        .preliticsWidget ul.preliticsWidgetList li.preliticsWidgetListItem a.preliticsWidgetListItemLink span.preliticsWidgetListItemName,
        .preliticsWidget ul.preliticsWidgetList li.preliticsWidgetListItem a.preliticsWidgetListItemLink span.preliticsWidgetListItemPrice { line-height: 15px; }
        .preliticsWidget ul.preliticsWidgetList li.preliticsWidgetListItem a.preliticsWidgetListItemLink span.preliticsWidgetListItemName { display: block; font-weight: bold; color: #2F3031; }
        .preliticsWidget ul.preliticsWidgetList li.preliticsWidgetListItem a.preliticsWidgetListItemLink span.preliticsWidgetListItemPrice { display: block; font-weight: bold; color: #666; }


        /* Horizontal Widget */
        .preliticsWidget.preliticsWidgetHorizontal {  }

        /* Vertical Widget */
        .preliticsWidget.preliticsWidgetVertical {  }
    </style>
```

### Version
2.0.0

### Support

If you require support integrating Prelitics onto your site then please drop us [an email](mailto:steve.goodwin@prelitics.com "Email Us")
