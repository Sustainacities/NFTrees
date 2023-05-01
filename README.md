
# NFTree Protocol Specification

## Version 1.0.0 (Initial Revision)

### Overview

The NFTree Protocol is a decentralized system designed to manage and track the planting, location, and details of trees on planet Earth. Utilizing the power of distributed systems and the benefits of Non-Fungible Tokens (NFTs), NFTree aims to provide a secure, transparent, and open platform for individuals, organizations, and governments to manage and monitor their reforestation efforts.

This protocol uses the data structure provided by the ArcGIS REST service at [https://services1.arcgis.com/ug7Y0GY6kYE0tf0p/arcgis/rest/services/Trees_Final/FeatureServer/0](https://services1.arcgis.com/ug7Y0GY6kYE0tf0p/arcgis/rest/services/Trees_Final/FeatureServer/0).

### Data Structure

The NFTree protocol utilizes the following data structure to store information about each tree:

-   `TreeID`: A unique identifier for each tree, generated using a combination of timestamp and geolocation
-   `Location`: The GPS coordinates (latitude and longitude) of the tree
-   `Species`: The species of the tree
-   `DatePlanted`: The date the tree was planted (YYYY-MM-DD)
-   `Height`: The height of the tree in meters
-   `Diameter`: The diameter of the tree in centimeters at breast height (DBH)
-   `HealthStatus`: The health status of the tree (healthy, diseased, dead, etc.)
-   `PlanterID`: The unique identifier of the individual, organization, or government that planted the tree
-   `Metadata`: Additional information about the tree, such as images or descriptions
- ### Protocol Functions

1.  **Mint NFT**: When a tree is planted, an NFT is minted, representing the unique digital asset associated with that tree.
    
    -   Function signature: `mintNFTree(address _to, uint256 _treeID, TreeData _treeData)`
2.  **Transfer Ownership**: NFTrees can be transferred between entities, allowing for the sale, gifting, or donation of trees and their associated environmental benefits.
    
    -   Function signature: `transferNFTree(address _from, address _to, uint256 _treeID)`
3.  **Update Tree Data**: Update the data associated with a specific tree, such as height, diameter, or health status.
    
    -   Function signature: `updateTreeData(uint256 _treeID, TreeData _newTreeData)`
4.  **Retrieve Tree Data**: Retrieve the data associated with a specific tree using its unique identifier.
    
    -   Function signature: `getTreeData(uint256 _treeID)`
5.  **List Trees by Planter**: Retrieve a list of trees planted by a specific planter, using the planter's unique identifier.
    
    -   Function signature: `getTreesByPlanter(address _planter)`

### Events

1.  **NFTreeMinted**: Emitted when a new NFTree is minted.
    
    -   Event signature: `NFTreeMinted(uint256 indexed treeID, address indexed planter)`
2.  **NFTreeTransferred**: Emitted when the ownership of an NFTree is transferred.
    
    -   Event signature: `NFTreeTransferred(uint256 indexed treeID, address indexed from, address indexed to)`
3.  **TreeDataUpdated**: Emitted when the data associated with a specific tree is updated.
    
    -   Event signature: `TreeDataUpdated(uint256 indexed treeID, TreeData newTreeData)`

### Future Revisions

As the NFTree Protocol evolves and new features or improvements are proposed, revisions to the protocol specification will be made. Each revision will be identified by an updated version number and will include a description of the changes, as well as

# The WHEAT Stack

Welcome to the shortest stack out there. This stack combines Worker functions, Hyperscript,  Eleventy, Alpine.js and Tailwind CSS to make static site authoring easy and minimal!

This stack requires minimal setup and ready to deploy on your favorite edge service or cloud.

There are some other goodies in here, but they change so often that it's probably not worth including here, just check the `package.json` file!

## Getting Started 

Just run the usual commands and peep the `package.json` file to see the available scripts and packages.

For the lazy:

- `npm i` to build that big ol' `node_modules` folder
- `npm run dev` to boot up that dev server and start building
- `npm run build` when you're ready to build a production bundle

**Bonus**
`npm run build && npx serve dist` will boot up a local server of your production site!

## Hyperscript

Hyperscript is a scripting language for doing front end web development. It is designed to make it very easy to respond to events and do simple DOM manipulation in code that is directly embedded on elements on a web page.
Learn more at https://hyperscript.org/

## Getting Started with Worker Functions

Worker functions can be thought of as REST, gRPC, graphql or other remote functions that perform tasks somewhere other than the device running the application. These functions are typically served from the same domain, which reduces cross-site security vulnerabilities, but you can also call remote functions from any domain, and whitelist the domain for access from your application.
The WHEAT stack comes pre-configured for running functions on Cloudflare Pages, but you are free to customize your worker functions as you see fit. 

Read more about cloudflare pages functions at https://developers.cloudflare.com/pages/platform/functions
Use the /functions folder to configure your worker functions.

## Deploying 
