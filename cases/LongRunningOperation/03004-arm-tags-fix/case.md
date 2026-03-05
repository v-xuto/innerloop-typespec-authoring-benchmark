# CASE 03004-arm-tags-fix

## prompt

Use azure-typespec-author to compare newNormalizedSwagger.json with oldNormalizedSwagger.json, identify any newly introduced tags, trace them back to the corresponding TypeSpec definitions, and remove them at the TypeSpec level.


![tags diff](tagsDiff.png)

### Input code
[Code Files](Attach)

## Expected output 

Find the extra tags in the oldNormalizedSwagger.json and locate on the releated typesspec operation then fix the typespec code.

Expected Changes:

1. `omitTags: true` would be introduced to the `@armResourceOperations(#{ omitTags: true })` to omit the tags added by the Interface automatically.

2. Then add the actual tags on the specific opeartion like `@tag("RouteFilterRules")`

``` ts
@armResourceOperations(#{ allowStaticRoutes: true, omitTags: true })
interface RouteFilters {
  /**
   * Gets the specified rule from a route filter.
   */
  @tag("RouteFilterRules")
  @get
  @route("/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Network/routeFilters/{routeFilterName}/routeFilterRules/{ruleName}")
  routeFilterRulesGet is RouteFilterRuleOps.ActionSync<
    RouteFilter,
    void,
    Response = ArmResponse<RouteFilterRule>,
    OverrideErrorType = CloudError
  >;
}

```
