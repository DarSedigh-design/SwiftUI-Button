import SwiftUI

// A reusable SwiftUI button component
struct CustomButton: View {
    var title: String // Button title text
    var action: () -> Void // Closure executed when button is tapped
    
    var body: some View {
        Button(action: action) { // Button with custom styling
            Text(title)
                .font(.headline) // Sets font to headline
                .foregroundColor(.white) // White text color
                .padding() // Adds padding around text
                .frame(maxWidth: .infinity) // Expands button width
                .background(Color.blue) // Sets background color to blue
                .cornerRadius(10) // Rounds corners with radius 10
                .shadow(radius: 5) // Adds a shadow effect
        }
        .padding(.horizontal) // Adds horizontal padding
    }
}

// Preview provider to see the button in Xcode's canvas
struct CustomButton_Previews: PreviewProvider {
    static var previews: some View {
        CustomButton(title: "Click Me") {
            print("Button clicked!") // Simulates button action in console
        }
        .previewLayout(.sizeThatFits) // Adjusts preview size to fit content
    }
}
