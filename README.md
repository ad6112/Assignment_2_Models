<h1>Notion App ERD</h1>

This ERD represents a simplified version of Notion's database structure on their desktop app, capturing some core entities and their relationships.

User --> Workspace --> Page --> Block

<h3>Entities</h3>

1. <strong>Users</strong>: Represents each individual users of the Notion platform, identified by a user ID. 

Primary Key: userId

Attributes: userId, email, firstName, lastName

2. <strong>Workspace</strong>: Represents workspaces where users organize their content. Each user can create multiple workspaces. In reality, multiple users can work on one workspace, but for simplicity, in my ERD I assumed that each workspace only belongs to one user.
Workspaces can be on the Free, Plus, Eduction Plus, Business, or Enterprise plans. 

Primary Key: workspaceId

Foreign Key: workspace.userId

Attributes: workspaceId, workspaceName, planType

3. Page: Represents individual pages within a workspace. Each workspace can have many pages. 

Primary Key: pageId

Foreign Keys: page.workspaceId, page.userId

Attributes: title, dateCreated

4. Block: Notion organizes its pages using content blocks within them. Each page has many blocks. These can be text, images, tables, headings, code/math blocks, and more. Blocks can have a color assigned to them.

Primary Key: blockId

Foreign Keys: pageId

Attributes: blockId, pageId, blockType, blockColor
