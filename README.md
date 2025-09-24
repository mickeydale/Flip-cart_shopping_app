Flip-Cart Shopping Application ::

This project is a modern, responsive web application built to demonstrate a practical understanding of key frontend technologies. It simulates a basic shopping experience where users can view products, add them to a cart, and see a summary of their selections. The application architecture is designed for scalability and maintainability, separating concerns between UI, state management, and data fetching.

Core Technologies and Their Roles:-
React: The application is built using a component-based architecture with React. Reusable components like Header, Home, and Cart manage their own state and render dynamic UIs. The main App component acts as the application's root, orchestrating the layout and routing.

Redux Toolkit: This library is used for centralized state management. Instead of passing data between components through props (prop drilling), the application uses a global store.

createSlice: defines the cartSlice, which contains the initial state (initialState = []) and the reducers (addToCart and removeFromCart). These reducers specify how the state can be modified in a predictable way.

configureStore: sets up the Redux store, connecting the cartReducer to the application.

useDispatch: is a React hook used in components like ProductTile and CartTile to dispatch actions (e.g., addToCart, removeFromCart) that trigger state changes in the store.

useSelector: is a hook that allows components to select and access specific parts of the Redux state, such as the cart array, and automatically re-render when that part of the state changes.

React Router DOM: This library handles all client-side routing within the single-page application.

The BrowserRouter wraps the entire application to enable routing.

The Routes component acts as a container for individual Route components, which define the paths and corresponding components to render.

The Link component is used to create navigation links (<Link to={"/"}>) that navigate between pages without requiring a full page reload, providing a fast and smooth user experience.

Tailwind CSS: This is a utility-first CSS framework used for styling the entire application. Instead of writing custom CSS, the UI is built by applying pre-defined utility classes directly in the JSX (e.g., flex, p-4, rounded-xl). This approach simplifies styling, ensures design consistency, and makes the application fully responsive by using responsive prefixes like sm: and md:.

External API Integration: The Home component uses the built-in fetch API to make an asynchronous GET request to https://fakestoreapi.com/products. The data is then stored in local state (useState), and a loading spinner from react-loader-spinner provides a positive user experience while the data is being fetched.
