  > Change Log (2025-11-05): – Updated distance rule to support ‘short walks only’ preference.

Apply these **if/else** checks to make sure plans are realistic and adapt to edge cases:

1. **Closed Venue**
  
  * If a museum or park is closed on that day → suggest a similar indoor option nearby.
2. **Over-Budget Meal**
  
  * If meal cost > user’s budget → switch to a cheaper restaurant of similar cuisine.
3. **Too Far or Long Travel**
  
  * If transfer on foot between activities > 25 min or > 5 km → pick a closer alternative that is a short walk away only.
4. **Weather Swap**
  
  * If rain or cold season likely → make sure at least one indoor activity replaces outdoor ones.
5. **Time Overrun**
  
  * If total planned time > available hours → shorten lunch or pick a nearer stop.
6. **Mobility Needs**
  
  * If mobility limits noted → choose step-free, short-walk options and include breaks.
7. **Dietary Needs**
  
  * If user is vegan or has dietary constraints → ensure all meals match or swap with compliant ones.
8. **Bookings**
  
  * If activity usually needs a ticket → just remind the user to book it; never simulate bookings.
