---
title: Financial Functions
keywords: Financial Functions
sidebar: forlang_sidebar
permalink: formula-language/financial-functions.html
folder: Forlang
hide_sidebar: false
comments: false
---


# Financial Functions

## DB

Calculates an asset's depreciation using the fixed declining balance (DB) method over a specified term.

**DB (assetCost, salvageValue, lifespan, period, months)**

AssetCost is the original cost or purchase price of the asset at the start of the calculation.

SalvageValue is the market value of the asset after it's expected useful life ends, sometimes this will be the value of the asset as spare parts.

Lifespan indicates for how many periods the asset is useful (it's useful life), and must be depreciated. Accounting standards vary on what lifespan is appropriate for different classes of assets, such as durable and non-durable goods.

Period indicates the number of units of time between detrimental calculations of the depreciation. If lifespan is measured in years, then the value specified for the period must also be in years.

Months allows you to specify the number of months in the first year, if the depreciation does not begin on the first day of the year. You might specify months based on when the asset was purchased new. If omitted, the calculation defaults to 12 which is equivalent to calculating starting from the first day of the year.

For some assets, alternative calculation methods such as the [DDB ()]() function may be more appropriate. Your accountant can tell you for which assets the fixed declining balance method is an acceptable means of calculating depreciation.


## DDB

Calculates an asset's depreciation using the double declining balance (DDB) or another weighted factor method over a specified term.

**DDB (assetCost, salvageValue, lifespan, period, weight)**

AssetCost is the original cost or purchase price of the asset at the start of the calculation.

SalvageValue is the market value of the asset after it's expected useful life ends, sometimes this will be the value of the asset as spare parts.

Lifespan indicates for how many periods the asset is useful (it's useful life), and must be depreciated. Accounting standards vary on what lifespan is appropriate for different classes of assets, such as durable and non-durable goods.

Period indicates the number of units of time between decremental calculations of the depreciation. If lifespan is measured in years, then the value specified for the period must also be in years.

Weight allows you to fine tune the calculation method. By default, the double declining balance method uses a factor of 2.

For some assets, alternative calculation methods such as the [DB ()]() function may be more appropriate. Your accountant can advise you for which assets the double declining balance method is an acceptable means of calculating depreciation, and what factors can be used when depreciating certain assets such as high-tech equipment or motor vehicles which exhibit accelerated depreciation in their first years of use.


## FV

Calculates the future value of an annuity having fixed payments and assuming a fixed interest rate or rate of return.

**FV (interestRate, nPeriod, payment, presentValue, paymentDue)**

InterestRate is the assumed interest rate per period. The future value calculation assumes no change in the interest rate over the course of the investment. If you anticipate interest rate fluctuations, you should calculate the future value incrementally over shorter periods in which the interest rate is held constant. In some calculations, the interestRate may be synonymous with an investments' expected growth or rate of return per period.

NPeriod is the total number of payment periods in an annuity. Each payment is assumed to be of the same amount, and occur at regular fixed time intervals. A payment earlier in the annuity will be invested for a longer period of time and therefore would accrue more interest than a payment made later in the annuity.

Payment is a fixed amount invested in the annuity at each period. Use a negative number to represent an outflow of cash paid out, and a positive number to represent an inflow of cash received. Calculating a future value requires either a non-zero series of payments or a presentValue.

PresentValue is the value of the investment at the beginning of the annuity. It represents the discounted value of a series of future payments, which over time could be worth a greater amount because they have accrued interest. If the annuity has no present value, then you must specify a non-zero payment amount.

PaymentDue is a numeric value of either 1 or 0, and indicates whether payments are invested in the annuity at the beginning of each period (1) or at the end of each period (0).

The interestRate and nPeriod arguments determine the frequency of payments. If interestRate is given as an annual rate, and nPeriod is 1 then payments are once per year. On the other hand, if nPeriod had been 4 then payments would occur quarterly. Please ensure you use consistent time values when specifying these arguments.


## INTRATE

Calculates the interest rate yielded by a security investment redeemable at a future date, such as a zero coupon bond.

**INTRATE (settlementDate, maturityDate, amount, redemptionValue, basis)**

SettlementDate is the date on which a security purchase is settled with the buyer taking possession of the security. Market conventions for settlement of trades vary by security and exchange. The settlement date may be substantially later than a security's issue date when it is traded on the secondary market.

MaturityDate is the date when the security can be redeemed. It ceases to accrue any further value after this date. The maturity date must be later than the settlementDate or an error value is returned.

Amount is the purchase price of the security. For positive interest, this amount will be smaller than the redemptionValue because it discounts interest that will be accrued over the time period the security is held.

RedemptionValue is the price a security holder may redeem their security for at the maturityDate. In some cases, this may be called the face value of the security.

Basis describes what accounting convention to use when counting days per calendar year, and days on which interest can accrue. If omitted, a basis consistent with United States National Association of Security Dealers (NASD) of 30/360 will be employed.


## IPMT

Calculates the interest portion of a payment due on an investment or loan with periodic, fixed payments and having a fixed rate of interest.

**IPMT (interestRate, periodNumber, nPeriods, presentValue, futureValue, paymentDue)**

InterestRate is a fixed rate of interest per period. This function assumes there is one payment made on each period, therefore in cases where you want to calculate quarterly or monthly payments you should adjust an annual interestRate accordingly by dividing it by the number of payments per year.

PeriodNumber identifies the period of the current payment, where the first payment has the number 1. The periodNumber must not exceed the total number of periods (nPeriods).

NPeriods is the total number of payments over the course of this investment or loan.

PresentValue is the discounted value of this series of future payments, if you could take a lump sum payment today and invest it at the fixed interestRate until the future date when this investment or loan had been repaid.

FutureValue is the expected value of this series of payments after the last payment has been made, where all previous payments have been accumulating interest at the fixed interestRate. When omitted, such as when this function is used for calculating loan payments that reduce an outstanding liability, the future value is assumed to be zero.

PaymentDue is a numeric value indicating that payments are due at the beginning of each period (1) or at the end of each period (0).

The IPMT () function calculates the portion of a fixed payment attributed to interest. If you need to calculate the portion of a fixed payment repaying loan principal, then use the PPMT () function. To calculate fixed payment amounts, use the [PMT ()]() function.


## IRR

Calculates an internal rate of return for a given series of cash flows represented by either positive (incoming) or negative (outgoing) numeric values.

**IRR (value_reference, estimate)**

Value_reference must be a column or range reference of numeric values representing cash outflows (payments) as negative numeric values, and cash inflows (income) as positive numeric values. Each cash flow must occur with a regular period. If payments occur at irregular intervals, then you must represent the cash flow periods as taking place on a period common to all cash flows, and at intervals without a cash flow specify a zero value. For example, if you finance the purchase of a television by taking a $300 loan with monthly payments of $110, but your payments do not start for three months, your series of cash flows would be monthly but would show three zero values for the months without payments (+300, 0, 0, 0, -110, -110, -110).

Estimate is an approximation close to what you expect the resulting internal rate of return to be. This function employs an iterative algorithm starting with this estimate and then repeatedly converging on a result that has a diminishing margin of error. If you do not provide an estimate, then this function uses 10 percent as it's starting point.

If after twenty iterations the margin of error has not closed to within 1/1000 basis point, then a #NUM error value will be returned.

The IRR() function has applications where you may be given a series of cash flows without an interest rate, such as in the retail financing example above, and wish to calculate what it's effective rate of interest would be. The internal rate is based on the period between cash flows, therefore when calculating payments that are not annual, you must annualize the internal rate.


## NPER

Calculates an investment's number of payment periods when the payment frequency, amount, and interest rate are held steady.

**NPER (interestRate, amount, presentValue, futureValue, paymentDue)**

InterestRate is the rate of interest per payment period. This numeric value must be held fixed for the duration of the investment. If you must calculate financing based on changes in interest rate then you will need to break up the calculation into several stages over which the interest rate is held constant.

Amount is the payment amount due each period. This numeric value must be constant over the duration of the investment.

PresentValue is a discounted value or lump sum payment that if taken today and invested at the interestRate would be worth the same as this series of fixed payments in the future.

FutureValue is the value after the last payment has been made. If this numeric value is omitted it is assumed to be zero (since this function is normally used in calculating loan repayment you will reach zero liability when the loan is finally paid off.)

PaymentDue indicates whether payments come due at the beginning of each payment period (1) or at the end of each payment period (0). If left unspecified, the default is to assume paymentDue occurs at the end of each payment period.


## NPV

Calculates an investment's Net Present Value given its expected rate or return and the cash flow represented as positive numeric values (income) and negative numeric values (payments).

**NPV (discountRate, value1, value2, ..., valueN)**

DiscountRate is the investment's expected rate of return over the life of the investment, expressed as a percentage growth (or decline) per payment period. In some applications this may be the fixed interest rate. This numeric value is used to discount cash flows paid into or received from the investment.

Value1, value2, ... valueN are any number of numeric values representing cash inflows (as positive numbers) or cash outflows (as negative numbers). These cash flows must occur at a fixed period (the same period at which the discountRate is expressed), although some cash flows may be zero. The order of the sequence is important, as value1 is assumed to occur (N-1) periods before valueN and will have been able to accrue that much more interest at the assumed discountRate.

By convention, the NPV () assumes cash flows occur at the end of each period. Consequently, the NPV () represents the present value as of the date one period's length before the first cash flow, value1, has been made. If you require flexibility in when cash flows occur (the beginning or end of each period), consider using the PV () function. However, it differs from NPV () in that NPV () allows cash flows of different amounts.

Only numeric values or text values convertible to numeric values may be passed to this function. If a column or range reference is passed as a value argument, only numeric values or text values convertible to numeric values are used.


## PMT

Calculates what the payment amount should be on a loan at a fixed interest rate requiring a fixed number of payments.

**PMT (interestRate, nPeriods, presentValue, futureValue, paymentDue)**

InterestRate is the interest rate for the loan.

NPeriods is the number of payments required to pay back the loan.

PresentValue is the current value of the loan (also called the principal), which is a lump sum that the future series of nPeriods payments (which accumulate interest at interestRate) is worth today.

FutureValue is the cash balance in the future (for a loan, this will typically be a loan liability balance of zero) following this series of fixed payments, accruing a fixed interestRate. If omitted, a default future value of 0 is used.

PaymentDue is a numeric value of either 1 or 0, and indicates whether payments are invested in the annuity at the beginning of each period (1) or at the end of each period (0).


## PPMT

Calculates the principal portion of a payment due on an investment or loan with periodic, fixed payments and having a fixed rate of interest.

**PPMT (interestRate, periodNumber, nPeriods, presentValue, futureValue, paymentDue)**

InterestRate is a fixed rate of interest per period. This function assumes there is one payment made on each period, therefore in cases where you want to calculate quarterly or monthly payments you should adjust an annual interestRate accordingly by dividing it by the number of payments per year.

PeriodNumber identifies the period of the current payment, where the first payment has the number 1. The periodNumber must not exceed the total number of periods (nPeriods).

NPeriods is the total number of payments over the course of this investment or loan.

PresentValue is the discounted value of this series of future payments, if you could take a lump sum payment today and invest it at the fixed interestRate until the future date when this investment or loan had been repaid.

FutureValue is the expected value of this series of payments after the last payment has been made, where all previous payments have been accumulating interest at the fixed interestRate. When omitted, such as when this function is used for calculating loan payments that reduce an outstanding liability, the future value is assumed to be zero.

PaymentDue is a numeric value indicating that payments are due at the beginning of each period (1) or at the end of each period (0).

The PPMT () function calculates the portion of a fixed payment attributed to principal. If you need to calculate the portion of a fixed payment repaying interest, then use the IPMT () function. To calculate fixed payment amounts, use the [PMT ()]() function.


## PV

Calculates an investment's present value by discounting what a series of fixed future payments is worth at a specified interest rate.



**PV(interestRate, nPeriods, amount, futureValue, paymentDue)**

InterestRate is the per-period rate of interest used to discount the future payments. For positive interest rates, the value of future payments diminishes (discounts) to what they are worth now. It is assumed you can reinvest the present value at interestRate to receive futureValue after nPeriods.

NPeriods are the total number of payment periods over the course of the annuity. If your retirement plan annuitizes in 35-years, and you make a fixed quarterly contribution into it, then you would use 35x4 or 140 as your total number of payment periods.

Amount is how much is paid (or received) each period. This amount must be constant over the course of the investment. If you need to calculate the Net Present Value of a series of variable payment amounts, then you should consider using the [NPV ()]() function.

FutureValue is the expected cash balance of the investment at culmination. If this argument is omitted, it will be assumed to be zero. In the common usage scenario of calculating loan repayments, a future value of zero represents having a zero liability when the loan is fully repaid. When specifying a zero future value, ensure that amount is non-zero (otherwise the loan could never be repaid). In retirement planning, you would normally estimate the future value you would like to have when you retire.

PaymentDue is a numeric value of either 1 or 0, and indicates whether payments are invested in the annuity at the beginning of each period (1) or at the end of each period (0).


## RATE

Calculates the per-period interest rate for a series of cash flows (an annuity).


**RATE (nPeriods, amount, presentValue, paymentDue, futureValue, estimate)**

NPeriods are the total number of cash flows, whether a payment (negative amount) or a receipt (positive amount) occurring periodically with a fixed time period between each cash flow.

Amount is the amount of cash paid (negative) or received (positive). It must be held constant over the course of the annuity.

PresentValue is the value today of the series of future payments. Payments made in the future are discounted by the interest rate being calculated, because it is assumed that at that interest rate a smaller sum could be invested today and would grow to the amount at a future time when that payment became due.

PaymentDue indicates whether cash flows occur at the beginning of each period (1) or at the end of each period (0). If not specified, the payments at the end of each period is assumed.

FutureValue is the accumulated balance attained after nPeriods payments have been made and accrued interest at the calculated rate. If left unspecified, the default future value is assumed to be zero (this represents reaching zero loan liability, when a loan has been fully repaid).

Estimate is an approximation of the interest rate used to start the calculation (which works by iteratively refining the estimate until it converges on the correct value). When no estimate is given a default of 10% is assumed.

## SLN

Calculates what the straight-line depreciation of an asset should be per period.



**SLN (assetCost, salvageValue, lifespan)**

AssetCost is the initial value of the asset when it was purchased new. This numeric value needs to be greater than the salvageValue (otherwise the asset would be appreciating in value).

SalvageValue is the market price you can get for an asset at the end of its useful life (lifespan periods). In some situations, this may represent the value of the asset's spare parts.

Lifespan is the useful life of the asset being depreciated measured in fixed-length time periods (usually years). The appropriate lifespan to use may vary with the kind of asset being depreciated.

Straight-line depreciation expresses an asset's depreciation at a constant rate per period. The asset is assumed to lose useful value no faster in the first period depreciation is calculated than in the last period. An accountant can advise you as to which assets the straight-line depreciation calculation method is suitable.


## SYD

Calculates depreciation of an asset using the sum of years' digits (SYD) calculation method.


**SYD (assetCost, salvageValue, lifespan, periodNumber)**

AssetCost is the initial value of the asset when it was purchased new. This numeric value needs to be greater than the salvageValue (otherwise the asset would be appreciating in value).

SalvageValue is the market price you can get for an asset at the end of its useful life (lifespan periods). In some situations, this may represent the value of the asset's spare parts.

Lifespan is the useful life of the asset being depreciated measured in fixed-length time periods (usually years). The appropriate lifespan to use may vary with the kind of asset being depreciated. As the name of this function suggests, the lifespan when using this depreciation method is normally measured in years (although this does not necessarily have to be the case).

PeriodNumber is the one-based number of the period to calculate the depreciation of the asset for, having a value of between 1 and lifespan. It must be measured in the same units of time as the lifespan.


## DOLLARDE

Converts a dollary amount expressed as a decimal into a dollar amount expressed as a fraction.



**DollarFr(decimalDollarAmount, Fraction)**

DecimalDollarAmount is the dollar amount expressed as a decimal.

Fraction is the value used as the denominator of the fraction. If this value is not an integer, it will be truncated.


## DOLLARFR

Converts a dollary amount expressed as a decimal into a dollar amount expressed as a fraction.



**DollarFr(decimalDollarAmount, Fraction)**

DecimalDollarAmount is the dollar amount expressed as a decimal.

Fraction is the value used as the denominator of the fraction. If this value is not an integer, it will be truncated.
