# CASE Remove extra tags

## prompt

Use azure-typespec-author to compare newNormalizedSwagger.json with oldNormalizedSwagger.json, identify any newly introduced tags, trace them back to the corresponding TypeSpec definitions, and remove them at the TypeSpec level.

## Description

We want to  use azure-typespec-author to compare newNormalizedSwagger.json with oldNormalizedSwagger.json, identify any newly introduced tags, and remove the extra tags from the new swagger.

![alt text](images/1772587819208.png)

## Expected output 

find the extra tags in the oldNormalizedSwagger.json and locate on the releated typesspec operation then fix the typespec code.
