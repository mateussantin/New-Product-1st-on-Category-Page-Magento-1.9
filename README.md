# New-Product-1st-on-Category-Page-Magento-1.9

## Copy `app/code/core/Mage/Catalog/Block/Product/List/Toolbar.php` to `app/code/local/Mage/Catalog/Block/Product/List/Toolbar.php` (create a new directory if it is not exists).

#### Open new file and look at these lines of code in around line 232
~~~php 
if ($this->getCurrentOrder()) {
  $this->_collection->setOrder($this->getCurrentOrder(), $this->getCurrentDirection());
}
~~~

#### Now, replace with these lines
~~~php 
if ($this->getCurrentOrder()) {
  if(($this->getCurrentOrder()) == 'position'){
    $this->_collection->setOrder('entity_id', 'desc');
  }
  else {
    $this->_collection->setOrder($this->getCurrentOrder(),$this->getCurrentDirection());
  }
}
~~~

#### Don't forget to clear the entire cache and the list is ready.
