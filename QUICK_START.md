# Quick Start Guide - Running BlazingPizza

## Step 1: Prerequisites Check
Verify you have .NET 9.0 installed:
```bash
dotnet --version
```

Should output: `9.x.x` or higher

## Step 2: Open Project in VS Code

```bash
cd c:\Users\hp\OneDrive\Desktop\BlazingPizza
code .
```

## Step 3: Build the Project

In the VS Code terminal:
```bash
dotnet build
```

Expected output: `Build succeeded.`

## Step 4: Run the Application

Option A - Using F5 in VS Code:
- Press `F5` or go to Run → Start Debugging

Option B - Using terminal:
```bash
dotnet run
```

Expected output:
```
info: Microsoft.Hosting.Lifetime[14]
      Now listening on: https://localhost:7172
      Now listening on: http://localhost:5000
```

## Step 5: Open in Browser

- Navigate to: `https://localhost:7172` (or the HTTPS port shown)
- Or: `http://localhost:5000` (if HTTPS fails)

## Step 6: Test the Features

### Test Navigation
1. Click "Get Pizza" - should be highlighted
2. Click "My Orders" - link should highlight
3. Notice the layout persists across pages

### Test Route Parameters
1. In address bar, go to: `https://localhost:7172/pizzasize/12`
2. See: "Your preferred pizza size: 12 inches"
3. Try: `https://localhost:7172/pizzasize/margherita` (should not match - not an int)

### Test Order Tracking
1. Click "Get Pizza" (home)
2. Select a pizza and configure it
3. Click "Order >" at bottom
4. Fill checkout and place order
5. You're redirected to order detail page with route parameter

### Test Catch-All Route
1. Go to: `https://localhost:7172/favoritepizzas/margherita/hawaiian/pepperoni`
2. See all pizzas parsed: "margherita/hawaiian/pepperoni"

## Troubleshooting

### Port Already in Use
If port 5000/7172 is in use:
```bash
dotnet run --urls "https://localhost:7173"
```

### Database Issues
If you see database errors:
1. Delete `pizza.db` file
2. Run `dotnet run` again (will recreate database)

### Browser Shows "Cannot Connect"
1. Check terminal output for actual port number
2. Make sure you're using HTTPS (https://...) not HTTP
3. Wait 5-10 seconds for app to fully start

### Missing Dependencies
```bash
dotnet restore
dotnet clean
dotnet build
```

## Taking Screenshots for Submission

### Screenshot 1: Home Page
- Show the pizza menu with header and navigation
- Proof the app is running and displaying content

### Screenshot 2: Order Tracking Page
- Navigate to `/myorders/1`
- Show the OrderDetail page with route parameter working
- Shows Addition #1: OrdersController integration

### Screenshot 3: Route Constraints Demo
- Navigate to `/pizzasize/12` or `/pizzaconstraints/true`
- Show the route parameter constraint working
- Shows Addition #2: Advanced routing examples

### Screenshot 4: My Orders Page
- Show the orders list
- Show the layout consistency across pages

## Success Indicators

✅ App loads without errors
✅ Home page displays pizza menu
✅ Navigation links work and highlight
✅ Can select and configure pizzas
✅ Checkout process works
✅ Order details page shows specific order
✅ Route parameters work with constraints
✅ All pages have consistent layout with header/footer
✅ No runtime errors in browser console
✅ Database persists between page refreshes

## Stopping the Application

- In terminal: Press `Ctrl + C`
- In VS Code: Press `Shift + F5` or click Stop Debugging

## Need Help?

Check the following files for reference:
- `ASSIGNMENT_SUBMISSION.md` - Full project documentation
- `LAYOUT_EXERCISE_COMPLETE.md` - Layout implementation details
- `README.md` - Original pizza delivery app overview
