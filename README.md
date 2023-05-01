
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
