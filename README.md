# StandardAlertDialog
Standard AlertDialog in Android using Java language

# **Usage** 
***
[1] **Add the following two functions in any class in your project** 

    private AlertDialog.Builder buildAlertDialog(Context context, String title, String message, String positiveBtn, String negativeBtn, boolean isCancelable){
        AlertDialog.Builder builder = new AlertDialog.Builder(context);                  // Create the object of AlertDialog Builder class
        builder.setMessage(message);                                                     // Set the message show for the Alert time
        builder.setTitle(title);                                                         // Set Alert Title
        builder.setCancelable(isCancelable);                                             // Set Cancelable false for when the user clicks on the outside the Dialog Box then it will remain show

        builder.setPositiveButton(positiveBtn, (dialog, which) -> { finish(); });        // Set the +ve btn with yes name Lambda OnClickListener method is use of DialogInterface interface. When the user click yes button then app will close
        builder.setNegativeButton(negativeBtn, (dialog, which) -> { dialog.cancel(); }); // Set the -ve button with No name Lambda OnClickListener method is use of DialogInterface interface. If user click no then dialog box is canceled.

        return builder;
    }
and 

    private void displayAlertDialog(AlertDialog.Builder builder){
        AlertDialog alertDialog = builder.create();                                      // Create the Alert dialog
        alertDialog.show();                                                              // Show the Alert Dialog box
        alertDialog.getWindow().setLayout(1000,1200);                        // Set Dialog screenSize
    }
***
[2] **Call the two functions in the activity/fragment you want to fire AlertDialog from**

    displayAlertDialog(buildAlertDialog(this,"Set Location on Map","Use the picker to set Location","Confirm","Cancel",false));
***
[3] **[Here](https://github.com/mossssama/StandardAlertDialog/blob/main/StandardAlertDialog/app/src/main/java/com/example/dialogmap/MainActivity.java) an example applying the previous two point to be click** 
***
