# PaypalExample
This is a paypal library.

Gradle :
	        implementation 'com.github.dpsharma1988:PaypalExample:0.1.0'
          
              private static final int PAYPAL_REQUEST_CODE = 7777;

          PaypalFactory paypalFactory = PaypalFactory.getInstance(this);
          paypalFactory.startPaypalService();
          
          Button btnPayNow = findViewById(R.id.btnPayNow);
           btnPayNow.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                processPayment();
            }
        });
        
        private void processPayment()
        {
          paypalFactory.openPaymentScreen(String.valueOf(edtAmount.getText().toString()));
        }
        
        
        
        @Override
    protected void onActivityResult(int requestCode, int resultCode, @Nullable Intent data) {
        super.onActivityResult(requestCode, resultCode, data);
        if (requestCode == PAYPAL_REQUEST_CODE) {
            if (resultCode == RESULT_OK) {
                boolean isPaymentConfirmed = paypalFactory.isPaymentConfirmed(data);
                if (isPaymentConfirmed) {
                        String paymentDetails = paypalFactory.getPaymentResultString(dat
                }
            } else if (resultCode == Activity.RESULT_CANCELED) {
//                Toast.makeText(this, "Cancel", Toast.LENGTH_SHORT).show();
            }
        } else if (resultCode == Const.INVALID_PAYMENT) {
//            Toast.makeText(this, "Invalid", Toast.LENGTH_SHORT).show();
        }
    }

