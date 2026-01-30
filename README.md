<a href="https://githubsfdeploy.herokuapp.com?owner=FinDockLabs&repo=gomeddo-booking-findock-source&ref=main">
  <img alt="Deploy to Salesforce"
       src="https://raw.githubusercontent.com/afawcett/githubsfdeploy/master/deploy.png">
</a>

# GoMeddo (Booking) FinDock integration

The repo includes Flows for creating PayLinks on confirmed reservations, tracking payment status, and handling payment completion.
It is intended as an implemenation starter

## Installation

Prerquisites:
- FinDock with at least one processor
- GoMeddo

### Step 0: Deploy the project
First deploy the project.
To deploy the flow to your Salesforce environment, you can:
- use `sfdx`.
- press the "Deploy to Salesforce" button at the top of this README and then press "Login to Salesforce" in the top right of your screen.
- any other deployment method you prefer.

### Step 1: Basic configuration
1. Activate the following Flows: RTF_Create_installment_from_Reservation and RTF_Reservation_Set_Deposit_amount
2. Assign the GoMeddo_For_FinDock permission set
3. Assign the Reservation With Installments layout or add the Installment fields on reservation to your existing layout

### Step 2: Create a PayLink template
1. Go to **FinDock Setup** > **PayLinks**
2. Add your logo and colors
3. Select your payment methods
4. Save & Publish

### Step 3: Add a payment rule
1. Go to Payment Rules
2. Add one or more Payment Rules to control when Installments are created

## How it works
1. Customer books a reservation
2. Flow creates an Installment with a FinDock PayLink
3. Customer receives the link (email, SMS, or portal)
4. Customer pays
5. FinDock updates the payment status of the Installment in Salesforce6. Reservation shows as paid (edited)


## Contributing

When contributing to this repository, please first discuss the change you wish to make via an issue or any other method with FinDock before making a change.

## Support

FinDock Labs is a non-supported group in FinDock that releases applications. Despite the name, assistance for any of these applications is not provided by FinDock Support because they are not officially supported features. For a list of these apps, visit the FinDock Labs account on Github. 

## License

This project is licensed under the MIT License - see the [LICENSE](/LICENSE) file for details