# Architecture

## Capability map
- Lunar date calculation for any selected day
- Vietnamese weekday and Can/Chi display
- Haircut guidance based on lunar day value
- Simple, mobile-friendly presentation layer

## Smart boxes
1. Date Input Box
   - Input: selected calendar date
   - Output: solar date object
   - Rules: validate date and update UI state

2. Lunar Calculation Box
   - Input: solar date
   - Output: lunar day, lunar month, Can/Chi, weekday
   - Rules: use a reliable lunar library and convert to Vietnamese labels

3. Haircut Interpretation Box
   - Input: lunar day number
   - Output: status, icon, meaning text
   - Rules: map lunar day to predefined good/bad haircut guidance

4. Presentation Box
   - Input: computed values and status metadata
   - Output: rendered UI card, badges, and styling
   - Rules: keep layout minimal and readable on mobile and desktop

## Connection plan
- Date Input → Lunar Calculation → Haircut Interpretation → Presentation
- Thin routing only; business meaning remains inside each box
- No dependency on backend services for the current simple build

## Contract summary
- Input date is a valid JS Date object
- Lunar output uses day/month and text labels in Vietnamese
- Haircut output returns one of: kiết, hung, or neutral
- Presentation layer renders status styles and localized text
