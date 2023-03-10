# How to show full name without ellipsis (…) in a Powershell Query

Sometimes, when property names contain very long values, the default displays cuts part of the name, as shown with this command and its output.

[“ellipsis” is the term for the … when a name is truncated] as shown in the example below:

get-service | where {$_.name -match "win"}  | sort-object Status -desc

 
Powershell_ouptut_normal_with_ellipses
Red box is only added to bring your attention to the …
Simply pipe the result to the “ft -auto” cmdlet.

get-service | where {$_.name -match "win"}  | sort-object Status -desc | ft -auto

Powershell_ouptut_ft_auto

The full name is now displayed

ft is just the abbreviation for format-table, so you could have typed:

get-service | where {$_.name -match "win"}  | sort-object Status -desc | format-table -auto


Or as was discussed in my previous blog, you can use the grid view:
get-service | where {$_.name -match “win”} | out-gridview

https://mylifeismymessage.net/how-to-show-full-name-without-ellipses-in-a-powershell-query/
