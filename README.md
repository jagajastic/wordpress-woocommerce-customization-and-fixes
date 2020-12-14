# WordPress, and Woocommerce customization and tweaks

## Remove 'Billing' from checkout error message

```
function customize_wc_errors( $error ) {
    if ( strpos( $error, 'Billing ' ) !== false ) {
        $error = str_replace("Billing ", "", $error);
    }
    return $error;
}
add_filter( 'woocommerce_add_error', 'customize_wc_errors' );
```

## Custom Validation on Checkout field

```
add_action('woocommerce_checkout_process', 'my_custom_checkout_field_process');
  
function my_custom_checkout_field_process() {
   //  global $woocommerce;

   // use the $_POST['field_name'] to access the field you want to validate
}
```

