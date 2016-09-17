# NAICSjson
North American Industry Classification System encoded into JSON format

This file includes all 2012 NAICS industries, accurate to 5 or 6 digits.

Note: Please be advised that there are no gaurantees to its accuracy.



1. HTML Markup
 
 <div>
		<select ng-options="ind.name for ind in MySectors " ng-model="naics.level1" required>
			 <option value="">Please Select</option>
		</select>
		
		<select ng-show="naics.sector" ng-options="ind.name for ind in naics.level1.subsectors" ng-model="naics.level2" required>
			 <option value="">Please Select</option>
		</select>
			
		<select ng-show="naics.subsector" ng-options="ind.name for ind in naics.level2.subsectors" ng-model="naics.level3" >
			  <option value="">Please Select</option>
		</select>
		
		<select ng-show="naics.industry" ng-options="ind.name for ind in naics.level3.subsectors" ng-model="naics.level4">
			 <option value="">Please Select</option>
		</select>
</div>



2. Insert into your (angular) controller:

	$http.get("path/to/subsectors.json").then(function(res){
        $scope.MySectors = res.data;
	});
