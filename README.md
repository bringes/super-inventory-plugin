# Super Inventory for Claude, ChatGPT and Codex

Super Inventory keeps track of what you own and exactly where it is stored, from a garage shelf to a warehouse bin.
This plugin connects your AI assistant to your Super Inventory account, so you can ask where something is, what is
running low or what is on your To Buy list, and, when you allow it, change stock, add new items and add to your
shopping list. Assistants that show cards (ChatGPT, Claude) draw the answers with your own photos and stock.

## What's inside

- **The Super Inventory connector**: the remote MCP server at `https://superinventory.bunnytech.app/mcp`
  (`.mcp.json` for Claude, `mcp.json` for ChatGPT and Codex).
- **A skill** (`skills/super-inventory/SKILL.md`) that teaches the assistant how the inventory is organised and how to
  use the tools well: finding items, low stock, changing stock, adding items, the shopping list, notes and invoices.

## Install

- **Claude** (claude.ai, Claude Desktop, Claude mobile): add Super Inventory from the Connectors directory, or the
  plugin from the plugin directory.
- **Claude Code**:
  ```
  /plugin install super-inventory --marketplace bringes/super-inventory-plugin
  ```
- **ChatGPT and Codex**: add Super Inventory from the Plugins directory.

## Requirements

A Super Inventory account, on any plan. Create one in the Super Inventory app or at
https://superinventory.bunnytech.app.

## Connecting

The first time a tool runs, the assistant opens Super Inventory's sign-in page. Sign in, choose the inventory to use,
and choose what the assistant may do:

- **Read your inventory** (always): items, places, stock, low stock, To Buy and To Do lists.
- **Make changes** (ticked by default, can be unticked): take out, put in, count or move stock, add items, add to the
  shopping list.
- **Read notes** and **read invoices and receipts** (unticked by default).

Disconnect at any time on the AI Assistants page in the app or on the web; the assistant's next request is refused.

## Tools

| Tool | What it does | Changes data |
| --- | --- | --- |
| `search_inventory` | Finds items and saved pages by words or inventory number | no |
| `filter_products` | Finds items by category, specifications and stock | no |
| `list_categories`, `get_facets` | The categories and the specifications to filter on | no |
| `get_product` | One item's details and its stock in each place | no |
| `list_locations`, `get_location_contents` | Places, and what is stored in one | no |
| `low_stock` | Items at or below their minimum | no |
| `list_checklists` | What is still open on To Buy, To Do and wishlists | no |
| `search_notes` | Notes by their words (only with notes allowed) | no |
| `search_invoices`, `invoice_totals` | Invoices and receipts, and spending per month or supplier (only with invoices allowed) | no |
| `change_stock` | Takes out, puts in, counts or moves stock in one place | yes |
| `add_to_shopping_list` | Adds an entry to a To Buy list or a wishlist | yes |
| `add_items` | Adds new items with their photos and product page | yes |

## Where your data goes

- The tools read and change your own Super Inventory account, on Bringes Technology's servers in the European Union.
  Nothing is sent anywhere else by the plugin.
- What a tool returns is sent to the assistant you use, and its maker's privacy policy applies to it.
- `add_items` downloads the product pages and photos you name from the public web, to save them with the new item.
- Item cards load your photos from `superinventory.bunnytech.app` through links that stop working after an hour.
- Every change is recorded in the item's history with the assistant's name.

Privacy policy: https://superinventory.bunnytech.app/privacy · Terms: https://superinventory.bunnytech.app/terms

## Support

Open an issue in this repository, or write to hello@bunnytech.app.

Made by Bringes Technology SRL. The plugin's files are under the MIT licence (`LICENSE`).
