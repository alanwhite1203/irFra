# Valuing Forward Rate Agreement (FRA)

Overview
A forward rate agreement, or FRA, is a forward contract between two parties in which one party will pay a fixed rate while the other party will pay a reference interest rate for a set future period. Similar to a swap, a FRA has two legs: a fixed leg and a floating leg. But each leg only has one cash flow. The party paying the fixed rate is usually referred to as the borrower, while the party receiving the floating rate is referred to as the lender.
Some people believe that a FRA is equivalent to a one-period vanilla swap. That is not completely true from valuation perspective. A FRA is usually settled and paid at the end of a forwarding period, called settle in arrear, while a regular swaplet is settled at the beginning of the forward period and paid at the end. Strictly speaking, FRAs need convexity adjustment. However, given FRA is such a simple product, the adjustment is very simple as well. 
FRAs are over-the-counter (OTC) derivatives. They are cash-settled with the payment based on the net difference between the floating interest rate and the fixed (reference) rate in the contract. Similar to a swap, a FRA has two legs associating with each party: a fixed leg and a floating leg. But each leg only has one cash flow. The party paying the fixed rate is usually referred to as the buyer, while the party receiving the floating rate is referred to as the seller.
A FRA can be used to hedge future interest rate or exchange rate exposure. The buyer hedges against the risk of rising interest rate whereas the seller hedges against the risk of falling interest rates. In other words, the buyer locks in the interest rate to protect against the increase of interest rates while the seller protects against the possible decrease of interest rates. A speculator can also use FRAs to make bets on future directional changes in interest rates. Market participants can also take advantage of price differences between an FRA and other interest rate instruments. FRAs are money market instruments that are liquid in all major currencies. This presentation provides an introduction to FRA product and valuation. 

	Keywords
Forward rate agreement, FRA, swaplet, financial product, valuation model.

	FRA Introduction
	A forward rate agreement, or FRA, is a forward contract between two parties in which one party will pay a fixed rate while the other party will pay a reference interest rate for a set future period.
	FRAs are over-the-counter (OTC) derivatives.
	They are cash-settled with the payment based on the net difference between the floating interest rate and the fixed (reference) rate in the contract.
	Similar to a swap, a FRA has two legs associating with each party: a fixed leg and a floating leg. But each leg only has one cash flow.
	The party paying the fixed rate is usually referred to as the buyer, while the party receiving the floating rate is referred to as the seller.

	Use of FRA
	A FRA can be used to hedge future interest rate or exchange rate exposure.
	The buyer hedges against the risk of rising interest rate whereas the seller hedges against the risk of falling interest rates.
	In other words, the buyer locks in the interest rate to protect against the increase of interest rates while the seller protects against the possible decrease of interest rates.
	A speculator can also use FRAs to make bets on future directional changes in interest rates.
	Market participants can also take advantage of price differences between an FRA and other interest rate instruments.
	FRAs are money market instruments that are liquid in all major currencies.

	FRA Payoff
	From the seller perspective, the payoff of a FRA at payment date T is given by
〖Payff〗_seller=Nτ(R-F)		(1)
where 
N- the notional;
 τ – accrual period in years (e.g., a 3 month period ≈ 3/12 = 0.25)
R – the fixed rate in simply compounding.
F – the realized floating rate in simply compounding
	From the puyer perspective, the payoff of the FRA at payment date T is given by
〖Payff〗_buyer=Nτ(F-R)		(2)

	Valuation
	Some people believe that a FRA is equivalent to a one-period vanilla swap. That is not completely true from valuation perspective. 
	A FRA is usually settled and paid at the end of a forwarding period, called settle in arrear, while a regular swaplet is settled at the beginning of the forward period and paid at the end. 
	Strictly speaking, FRAs need convexity adjustment. However, given FRA is such a simple product, the adjustment is very simple as well.
	The present value of a fixed leg is given by
〖PV〗_fixed=RNτD/(1+Rτ)		(3)
where
	t   –  valuation date
	R  – fixed rate
	N  – notational principal amount
	T_1 – end time of the forwarding period
	T_0 – start time of the forwarding period
	τ=τ(T_0,T_1)  – accrual period (T_0,T_1).
	D=D(t,T_1)  –  discount factor

	The present value of a floating leg can be expressed as
〖PV〗_floating=(F+s)NτD/(1+Fτ)		(4)
where
	F=F(t;T_0,T_1) – simply compounded forward rate
	s -  floating spread
	The present value of an interest rate swap can expressed as
	For the payer perspective, PV=〖PV〗_float-〖PV〗_fixed		
	From the receiver perspective, PV=〖PV〗_fixed-〖PV〗_float

	Practical Guide
	Usually a FRA is settled at arrear, i.e,  the end of a forwarding period while a swaplet is settled at the beginning of the forward period, although both are paid at the end. The denominators in (3) and (3) are reflected the adjustment to this difference.
	Using fixed leg as an example, we first calculate the payoff NRτ at the end of the period. The payoff needs to be discounted to the start date as NRτ⁄((1+Rτ)). Finally the amount is discounted from the payment date or end date.
	Any compounded interest zero rate curves can be used to compute discount factor, of course the formulas will be slightly different. The most common used one is continuously compounded zero rates.
	To use the formula, you need to compute simply compounded forward rate instead of other compounding types.
	The accrual period is calculated according to the start date and end date of a cash flow plus day count convention 
	We assume that accrual periods are the same as forwarding periods and payment dates are the same as accrual end dates in the above formulas for brevity. But in fact, they are slightly different due to different market conventions.

	A real world example
Leg 1 Specification	Leg 2 Specification
Currency	USD	Currency	USD
Day Count	dcAct360	Day Count	dcAct360
Leg Type	Fixed	Leg Type	Float
Notional	250000000	Notional	250000000
Pay Receive	Pay	Pay Receive	Receive
Start Date	4/7/2017	Start Date	4/7/2017
End Date	10/10/2017	End Date	10/10/2017
Settlement Date	10/10/2017	Settlement Date	10/10/2017
Fixed Rate	0.014399	Spread	-0.014399
		Index Specification
		Type	LIBOR
		Tenor	6M
		Day Count	dcAct360


References:

https://finpricing.com/lib/EqLookback.html

https://bitbucket.org/cmrm11/irfra/downloads/IrFra-33.pdf


