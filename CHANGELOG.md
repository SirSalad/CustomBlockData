# Changelog

## 2.0.0
- CustomBlockData can now automatically keep track of changes made to blocks.
  - It can automatically remove custom block data when a block gets broken, replaced, has melted, etc
  - It can automatically move the data to the new location when a block was pushed by a piston
  - You can make certain blocks "protected", so that their data will never be affected by changes to the underlying block
  - Every automatic block data change calls custom cancellable events. See Javadocs
  - This feature is disabled by default to keep backwards compatibility. To enable it, simply call CustomBlockData#registerListener(Plugin)
- Added a few handy utility methods, for example
  - `void copyTo(Block, Plugin)` - Copies the current block's data to another block
  - `static boolean hasCustomBlockData(Block, Plugin)` - Checks if a given block has custom block data
  - `PersistentDataType<?,?> getDataType(NamespavedKey)` - Returns the correct primitive PersistentDataType associated with this NamespacedKey. Also available as static method
- Changed license from GNU GPLv3 to Apache License 2.0