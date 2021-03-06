# Event Collector metrics and guarantees

Metrics categorized by pattern and guarantees for the project Event Collector.

# Index

  * **[Metrics](#metrics)**
    * [PATTERN 1](#PATTERN_1) - Number of `[Event]` in `[Tool]` every `[Period]` by `[TEAM|MEMBER]`
      * [NUMBER_PT_STARTEDSTORIES](#NUMBER_PT_STARTEDSTORIES)
      * [NUMBER_PT_FINISHEDSTORIES](#number_pt_finishedstories)
      * [NUMBER_PT_ACCEPTEDSTORIES](#number_pt_acceptedstories)
      * [NUMBER_PT_DELIVEREDSTORIES](#number_pt_deliveredstories)
      * [NUMBER_GH_NEWBRANCH](#number_gh_newbranch)
      * [NUMBER_GH_OPENPR](#number_gh_openpr)
      * [NUMBER_GH_MERGEPR](#number_gh_mergepr)
      * [NUMBER_HE_RELEASES](#number_he_releases)
      * [NUMBER_TR_BUILDS](#number_tr_builds)
      * [NUMBER_TR_FAILEDBUILDS](#number_tr_failedbuilds)
      * [NUMBER_CC_COVERAGE](#number_cc_coverage)
      * [NUMBER_CC_COVERAGE_OVER80](#number_cc_coverage_over80)
    * [PATTERN 2](#PATTERN_2) - `[MAX|MIN|AVG|STD|NEWEST|LATEST]` `[Property]` value of `[Event]` in `[Tool]` every `[Period]` by team.
      * [VALUE_CC_COVERAGE](#value_cc_coverage)
      * [VALUE_CC_COVERAGE_OFFSET](#value_cc_coverage_offset)
    * [PATTERN 3](#PATTERN_3) - `[Frequency]` distribution of `[Event]` in `[Tool]` every `[Period]` by team.
      * [STDEV_GH_MERGEPR_DAILY](#stdev_gh_mergepr_daily)
    * [PATTERN 4](#PATTERN_4) - Percentage of `[Event1]` in `[Tool1]` correlated with `[Event2]` in `[Tool2]` within `[window]` every `[Period]` by team.
      * [PERCENTAGE_GH_NEWBRANCH_PT_STARTEDSTORIES](#percentage_gh_newbranch_pt_startedstories)
      * [PERCENTAGE_GHWR_NEWBRANCH_PT_STARTEDSTORIES](#percentage_ghwr_newbranch_pt_startedstories)
      * [PERCENTAGE_GH_NEWBRANCH_PT_STARTEDSTORIES_BIND](#percentage_gh_newbranch_pt_startedstories_bind)
      * [PERCENTAGE_GH_OPENPR_PT_FINISHEDSTORIES](#percentage_gh_openpr_pt_finishedstories)
      * [PERCENTAGE_GH_OPENPR_PT_FINISHEDSTORIES_BIND](#percentage_gh_openpr_pt_finishedstories_bind)
      * [PERCENTAGE_GH_MERGEPR_PT_DELIVEREDSTORIES](#percentage_gh_mergepr_pt_deliveredstories)
      * [PERCENTAGE_GH_MERGEPR_PT_DELIVEREDSTORIES_BIND](#percentage_gh_mergepr_pt_deliveredstories_bind)
      * [PERCENTAGE_HE_RELEASES_PT_DELIVEREDSTORIES](#percentage_he_releases_pt_deliveredstories)
      * [PERCENTAGE_HE_RELEASES_PT_DELIVEREDSTORIES_BIND](#percentage_he_releases_pt_deliveredstories_bind)
      * [PERCENTAGE_TR_SUCCESSFULBUILDS_TR_BUILDS](#percentage_tr_successfulbuilds_tr_builds)
      * [PERCENTAGE_CC_COVERAGEOVER80_CC_COVERAGE](#percentage_cc_coverageover80_cc_coverage)
  * **[Guarantees](#guarantees)**
    * [75_PERCENT_NEWBRANCH_STARTED_STORIES_WITHIN_A_DAY_WRAPPER](#75_percent_newbranch_started_stories_within_a_day_wrapper)
    * [75_PERCENT_NEWBRANCH_STARTED_STORIES_WITHIN_A_DAY](#75_percent_newbranch_started_stories_within_a_day)
    * [75_PERCENT_NEWBRANCH_STARTED_STORIES_WITHIN_A_DAY_BIND](#75_percent_newbranch_started_stories_within_a_day_bind)
    * [75_PERCENT_MASTER_PR_OPEN_FINSH_STORIES_WITHIN_A_DAY](#75_percent_master_pr_open_finsh_stories_within_a_day)
    * [75_PERCENT_MASTER_PR_OPEN_FINSH_STORIES_WITHIN_A_DAY_BIND](#75_percent_master_pr_open_finsh_stories_within_a_day_bind)
    * [75_PERCENT_MASTER_PR_MERGE_DELVR_STORIES_WITHIN_A_DAY](#75_percent_master_pr_merge_delvr_stories_within_a_day)
    * [75_PERCENT_MASTER_PR_MERGE_DELVR_STORIES_WITHIN_A_DAY_BIND](#75_percent_master_pr_merge_delvr_stories_within_a_day_bind)
    * [75_PERCENT_MASTER_PR_MERGE_DEPLOY_WITHIN_A_DAY](#75_percent_master_pr_merge_deploy_within_a_day)
    * [75_PERCENT_MASTER_PR_MERGE_DEPLOY_WITHIN_A_DAY_BIND](#75_percent_master_pr_merge_deploy_within_a_day_bind)
    * [COVERAGE_DELTA_VARIATION_HIGHER_EQUAL_ZERO](#coverage_delta_variation_higher_equal_zero)
# Metrics

## PATTERN_1 
 - Number of `[Event]` in `[Tool]` every `[Period]` by `[TEAM|MEMBER]`

### NUMBER_PT_STARTEDSTORIES
Returns the total number of Pivotal started stories for the period requested.
``` json
{
  "NUMBER_PT_STARTEDSTORIES": {
    "computer": {
      "$ref": "#/context/definitions/computers/eventcomputer"
    },
    "metric": {
      "computing": "actual",
      "element": "number",
      "event": {
        "pivotal": {
          "activity": {
            "highlight": "started"
          }
        }
      },
      "scope": {
        "$ref": "#/context/definitions/scopes/development"
      }
    }
  }
}
```

### NUMBER_PT_FINISHEDSTORIES
Returns the total number of Pivotal finished stories for the period requested.
``` json
{
  "NUMBER_PT_FINISHEDSTORIES": {
    "computer": {
      "$ref": "#/context/definitions/computers/eventcomputer"
    },
    "metric": {
      "computing": "actual",
      "element": "number",
      "event": {
        "pivotal": {
          "activity": {
            "highlight": "finished"
          }
        }
      },
      "scope": {
        "$ref": "#/context/definitions/scopes/development"
      }
    }
  }
}
```

### NUMBER_PT_ACCEPTEDSTORIES
Returns the total number of Pivotal accepted stories for the period requested.
``` json
{
  "NUMBER_PT_ACCEPTEDSTORIES": {
    "computer": {
      "$ref": "#/context/definitions/computers/eventcomputer"
    },
    "metric": {
      "computing": "actual",
      "element": "number",
      "event": {
        "pivotal": {
          "activity": {
            "highlight": "accepted"
          }
        }
      },
      "scope": {
        "$ref": "#/context/definitions/scopes/development"
      }
    }
  }
}
```

### NUMBER_PT_DELIVEREDSTORIES
Returns the total number of Pivotal delivered stories for the period requested.
``` json
{
  "NUMBER_PT_DELIVEREDSTORIES": {
    "computer": {
      "$ref": "#/context/definitions/computers/eventcomputer"
    },
    "metric": {
      "computing": "actual",
      "element": "number",
      "event": {
        "pivotal": {
          "activity": {
            "highlight": "delivered"
          }
        }
      },
      "scope": {
        "$ref": "#/context/definitions/scopes/development"
      }
    }
  }
}
```

### NUMBER_GH_NEWBRANCH
Returns the number of branches created on GitHub for the period requested.
``` json
{
  "NUMBER_GH_NEWBRANCH": {
    "computer": {
      "$ref": "#/context/definitions/computers/eventcomputer"
    },
    "metric": {
      "computing": "actual",
      "element": "number",
      "event": {
        "ghwrapper": {
          "events": {
            "type": "CreateEvent",
            "payload": {
              "ref_type": "branch"
            }
          }
        }
      },
      "scope": {
        "$ref": "#/context/definitions/scopes/development"
      }
    }
  }
}
```

### NUMBER_GH_OPENPR
Returns the number of open pull requests on GitHub for the period requested.
``` json
{
  "NUMBER_GH_OPENPR": {
    "computer": {
      "$ref": "#/context/definitions/computers/eventcomputer"
    },
    "metric": {
      "computing": "actual",
      "element": "number",
      "event": {
        "github": {
          "allPR": {}
        }
      },
      "scope": {
        "$ref": "#/context/definitions/scopes/development"
      }
    }
  }
}
```

### NUMBER_GH_MERGEPR
Returns the number of open pull requests on GitHub for the period requested.
``` json
{
  "NUMBER_GH_MERGEPR": {
    "computer": {
      "$ref": "#/context/definitions/computers/eventcomputer"
    },
    "metric": {
      "computing": "actual",
      "element": "number",
      "event": {
        "github": {
          "mergedPR": {
            "base": {
              "label": "%GITHUB.REPO_OWNER%:master"
            }
          }
        }
      },
      "scope": {
        "$ref": "#/context/definitions/scopes/development"
      }
    }
  }
}
```

### NUMBER_HE_RELEASES
Returns the number of completed deployments on Heroku for the period requested.
``` json
{
  "NUMBER_HE_RELEASES": {
    "computer": {
      "$ref": "#/context/definitions/computers/eventcomputer"
    },
    "metric": {
      "computing": "actual",
      "element": "number",
      "event": {
        "heroku": {
          "releases": {
            "status": "succeeded",
            "description": "%CONTAINS%Deploy"
          }
        }
      },
      "scope": {
        "$ref": "#/context/definitions/scopes/development"
      }
    }
  }
}
```

### NUMBER_TR_BUILDS
Returns the total number of Travis builds for the period requested.
``` json
{
  "NUMBER_TR_BUILDS": {
    "computer": {
      "$ref": "#/context/definitions/computers/eventcomputer"
    },
    "metric": {
      "computing": "actual",
      "element": "number",
      "event": {
        "travis": {
          "builds_public": {
            "@type": "build"
          }
        }
      },
      "scope": {
        "$ref": "#/context/definitions/scopes/development"
      }
    }
  }
}
```

### NUMBER_TR_FAILEDBUILDS
Returns the total number of Travis builds that failed for the period requested.
``` json
{
  "NUMBER_TR_FAILEDBUILDS": {
    "computer": {
      "$ref": "#/context/definitions/computers/eventcomputer"
    },
    "metric": {
      "computing": "actual",
      "element": "number",
      "event": {
        "travis": {
          "builds_public": {
            "@type": "build",
            "state": "failed"
          }
        }
      },
      "scope": {
        "$ref": "#/context/definitions/scopes/development"
      }
    }
  }
}
```

### NUMBER_CC_COVERAGE
Returns the total number of CodeClimate reports with coverage higher or equal than 0 (all) for the period requested.
``` json
{
  "NUMBER_CC_COVERAGE": {
    "computer": {
      "$ref": "#/context/definitions/computers/eventcomputer"
    },
    "metric": {
      "computing": "actual",
      "element": "number",
      "event": {
        "codeclimate": {
          "coverage": {
            "data": {
              "attributes": {
                "covered_percent": "%HIGHER_OR_EQUAL%0"
              }
            }
          }
        }
      },
      "scope": {
        "$ref": "#/context/definitions/scopes/development"
      }
    }
  }
}
```

### NUMBER_CC_COVERAGE_OVER80
Returns the total number of CodeClimate reports with coverage higher than 80 for the period requested.
``` json
{
  "NUMBER_CC_COVERAGE_OVER80": {
    "computer": {
      "$ref": "#/context/definitions/computers/eventcomputer"
    },
    "metric": {
      "computing": "actual",
      "element": "number",
      "event": {
        "codeclimate": {
          "coverage": {
            "data": {
              "attributes": {
                "covered_percent": "%HIGHER%80"
              }
            }
          }
        }
      },
      "scope": {
        "$ref": "#/context/definitions/scopes/development"
      }
    }
  }
}
```

## PATTERN_2
 - `[MAX|MIN|AVG|STD|NEWEST|LATEST]` `[Property]` value of `[Event]` in `[Tool]` every `[Period]` by team.

### VALUE_CC_COVERAGE
Returns the newest value of coverage from CodeClimate for the requested period.
``` json
{
  "VALUE_CC_COVERAGE": {
    "computer": {
      "$ref": "#/context/definitions/computers/eventcomputer"
    },
    "metric": {
      "computing": "actual",
      "element": {
        "value": {
          "parameter": "attributes.covered_percent",
          "return": "newest",
          "traceback": true
        }
      },
      "event": {
        "codeclimate": {
          "coverage": {}
        }
      },
      "scope": {
        "$ref": "#/context/definitions/scopes/development"
      }
    }
  }
}
```



### VALUE_CC_COVERAGE_OFFSET
Returns the newest value of coverage from CodeClimate for the requested period offseted by 1 day.
``` json
{
  "VALUE_CC_COVERAGE_OFFSET": {
    "computer": {
      "$ref": "#/context/definitions/computers/eventcomputer"
    },
    "metric": {
      "computing": "actual",
      "element": {
        "value": {
          "parameter": "attributes.covered_percent",
          "return": "newest",
          "traceback": true
        }
      },
      "event": {
        "codeclimate": {
          "coverage": {}
        }
      },
      "scope": {
        "$ref": "#/context/definitions/scopes/development"
      },
      "offset": -1
    }
  }
}
```

## PATTERN_3
 - `[Frequency]` distribution of `[Event]` in `[Tool]` every `[Period]` by team.

### STDEV_GH_MERGEPR_DAILY
Returns the standard deviation of PR merges taking daily values as input from GitHub.
``` json
{
  "STDEV_MASTER_PR_MERGE": {
    "computer": {
      "$ref": "#/context/definitions/computers/eventcomputer"
    },
    "metric": {
      "computing": "string",
      "element": {
        "stdev": {
          "period": "daily"
        }
      },
      "event": {
        "github": {
          "closedPR": {
            "base": {
              "label": "%GITHUB.REPO_OWNER%:master"
            }
          }
        }
      },
      "scope": {
        "$ref": "#/context/definitions/scopes/development"
      }
    }
  }
}
```


## PATTERN_4
 - Percentage of `[Event1]` in `[Tool1]` correlated with `[Event2]` in `[Tool2]` within `[window]` every `[Period]` by team.

### PERCENTAGE_GH_NEWBRANCH_PT_STARTEDSTORIES
Returns the percentage obtained dividing the number of branches created on Github by the number of started stories on Pivotal for the requested period.
``` json
{
  "PERCENTAGE_GH_NEWBRANCH_PT_STARTEDSTORIES": {
    "computer": {
      "$ref": "#/context/definitions/computers/eventcomputer"
    },
    "metric": {
      "computing": "actual",
      "element": {
        "percentage": {
          "related": {
            "github": {
              "events": {
                "type": "CreateEvent",
                "payload": {
                  "ref_type": "branch"
                }
              }
            },
            "window": 86400
          }
        }
      },
      "event": {
        "pivotal": {
          "activity": {
            "highlight": "started"
          }
        }
      },
      "scope": {
        "$ref": "#/context/definitions/scopes/development"
      }
    }
  }
}
```

### PERCENTAGE_GHWR_NEWBRANCH_PT_STARTEDSTORIES
Returns the percentage obtained dividing the number of branches created on Github (obtained by the GitHub Wrapper) by the number of started stories on Pivotal for the requested period.
``` json
{
  "PERCENTAGE_GHWR_NEWBRANCH_PT_STARTEDSTORIES": {
    "computer": {
      "$ref": "#/context/definitions/computers/eventcomputer"
    },
    "metric": {
      "computing": "actual",
      "element": {
        "percentage": {
          "related": {
            "ghwrapper": {
              "events": {
                "type": "CreateEvent",
                "payload": {
                  "ref_type": "branch"
                }
              }
            },
            "window": 86400
          }
        }
      },
      "event": {
        "pivotal": {
          "activity": {
            "highlight": "started"
          }
        }
      },
      "scope": {
        "$ref": "#/context/definitions/scopes/development"
      }
    }
  }
}
```

### PERCENTAGE_GH_NEWBRANCH_PT_STARTEDSTORIES_BIND
Returns the percentage obtained dividing the number of branches created on Github by the number of started stories on Pivotal that are correlated with the binding parameter for the requested period.
``` json
{
  "PERCENTAGE_GH_NEWBRANCH_PT_STARTEDSTORIES_BIND": {
    "computer": {
      "$ref": "#/context/definitions/computers/eventcomputer"
    },
    "metric": {
      "computing": "actual",
      "element": {
        "percentage": {
          "related": {
            "github": {
              "events": {
                "type": "CreateEvent",
                "payload": {
                  "ref": "#CONTAINS(changes.0.id)#",
                  "ref_type": "branch"
                }
              }
            },
            "window": 86400
          }
        }
      },
      "event": {
        "pivotal": {
          "activity": {
            "highlight": "started"
          }
        }
      },
      "scope": {
        "$ref": "#/context/definitions/scopes/development"
      }
    }
  }
}
```

### PERCENTAGE_GH_OPENPR_PT_FINISHEDSTORIES
Returns the percentage obtained dividing the number of pull requests opened on Github by the number of finished stories on Pivotal for the requested period.
``` json
{
  "PERCENTAGE_GH_OPENPR_PT_FINISHEDSTORIES": {
    "computer": {
      "$ref": "#/context/definitions/computers/eventcomputer"
    },
    "metric": {
      "computing": "actual",
      "element": {
        "percentage": {
          "related": {
            "github": {
              "allPR": {}
            },
            "window": 86400
          }
        }
      },
      "event": {
        "pivotal": {
          "activity": {
            "highlight": "finished"
          }
        }
      },
      "scope": {
        "$ref": "#/context/definitions/scopes/development"
      }
    }
  }
}
```

### PERCENTAGE_GH_OPENPR_PT_FINISHEDSTORIES_BIND
Returns the percentage obtained dividing the number of pull requests opened on Github by the number of finished stories on Pivotal that are correlated with the binding parameter for the requested period.
``` json
{
  "PERCENTAGE_GH_OPENPR_PT_FINISHEDSTORIES_BIND": {
    "computer": {
      "$ref": "#/context/definitions/computers/eventcomputer"
    },
    "metric": {
      "computing": "actual",
      "element": {
        "percentage": {
          "related": {
            "github": {
              "allPR": {
                "head": {
                  "ref": "#CONTAINS(changes.0.id)#"
                }
              }
            },
            "window": 86400
          }
        }
      },
      "event": {
        "pivotal": {
          "activity": {
            "highlight": "finished"
          }
        }
      },
      "scope": {
        "$ref": "#/context/definitions/scopes/development"
      }
    }
  }
}
```

### PERCENTAGE_GH_MERGEPR_PT_DELIVEREDSTORIES
Returns the percentage obtained dividing the number of merged pull requests on Github by the number of delivered stories on Pivotal for the requested period.
``` json
{
  "PERCENTAGE_GH_MERGEPR_PT_DELIVEREDSTORIES": {
    "computer": {
      "$ref": "#/context/definitions/computers/eventcomputer"
    },
    "metric": {
      "computing": "actual",
      "element": {
        "percentage": {
          "related": {
            "github": {
              "mergedPR": {
                "base": {
                  "label": "%GITHUB.REPO_OWNER%:master"
                }
              }
            },
            "window": 86400
          }
        }
      },
      "event": {
        "pivotal": {
          "activity": {
            "highlight": "delivered"
          }
        }
      },
      "scope": {
        "$ref": "#/context/definitions/scopes/development"
      }
    }
  }
}
```

### PERCENTAGE_GH_MERGEPR_PT_DELIVEREDSTORIES_BIND
Returns the percentage obtained dividing the number of merged pull requests on Github by the number of delivered stories on Pivotal that are correlated with the binding parameter for the requested period.
``` json
{
  "PERCENTAGE_GH_MERGEPR_PT_DELIVEREDSTORIES_BIND": {
    "computer": {
      "$ref": "#/context/definitions/computers/eventcomputer"
    },
    "metric": {
      "computing": "actual",
      "element": {
        "percentage": {
          "related": {
            "github": {
              "mergedPR": {
                "head": {
                  "ref": "#CONTAINS(changes.0.id)#"
                }
              }
            },
            "window": 86400
          }
        }
      },
      "event": {
        "pivotal": {
          "activity": {
            "highlight": "delivered"
          }
        }
      },
      "scope": {
        "$ref": "#/context/definitions/scopes/development"
      }
    }
  }
}
```

### PERCENTAGE_HE_RELEASES_PT_DELIVEREDSTORIES
Returns the percentage obtained dividing the number of Heroku deployments by the number of delivered stories on Pivotal that are correlated within a really small period of time for the requested period.
``` json
{
  "PERCENTAGE_HE_RELEASES_PT_DELIVEREDSTORIES": {
    "computer": {
      "$ref": "#/context/definitions/computers/eventcomputer"
    },
    "metric": {
      "computing": "actual",
      "element": {
        "percentage": {
          "related": {
            "heroku": {
              "releases": {
                "status": "succeeded",
                "description": "%CONTAINS%Deploy"
              }
            },
            "window": 86400
          }
        }
      },
      "event": {
        "pivotal": {
          "activity": {
            "highlight": "delivered"
          }
        }
      },
      "scope": {
        "$ref": "#/context/definitions/scopes/development"
      }
    }
  }
}
```

### PERCENTAGE_HE_RELEASES_PT_DELIVEREDSTORIES_BIND
Returns the percentage obtained dividing the number of Heroku deployments by the number of delivered stories on Pivotal that are correlated within a really small period of time for the requested period.
``` json
{
  "PERCENTAGE_HE_RELEASES_PT_DELIVEREDSTORIES": {
    "computer": {
      "$ref": "#/context/definitions/computers/eventcomputer"
    },
    "metric": {
      "computing": "actual",
      "element": {
        "percentage": {
          "related": {
            "heroku": {
              "releases": {
                "status": "succeeded",
                "description": "%CONTAINS%Deploy"
              }
            },
            "window": 1440
          }
        }
      },
      "event": {
        "pivotal": {
          "activity": {
            "highlight": "delivered"
          }
        }
      },
      "scope": {
        "$ref": "#/context/definitions/scopes/development"
      }
    }
  }
}
```

### PERCENTAGE_TR_SUCCESSFULBUILDS_TR_BUILDS
Returns the percentage obtained dividing the number of Travis failed builds by the number of total Travis builds for the requested period.
``` json
{
  "PERCENTAGE_TR_SUCCESSFULBUILDS_TR_BUILDS": {
    "computer": {
      "$ref": "#/context/definitions/computers/eventcomputer"
    },
    "metric": {
      "computing": "actual",
      "element": {
        "percentage": {
          "related": {
            "travis": {
              "builds_public": {
                "@type": "build",
                "state": "failed"
              }
            },
            "window": 86400
          }
        }
      },
      "event": {
        "travis": {
          "builds_public": {
            "@type": "build"
          }
        }
      },
      "scope": {
        "$ref": "#/context/definitions/scopes/development"
      }
    }
  }
}
```

### PERCENTAGE_CC_COVERAGEOVER80_CC_COVERAGE
Returns the percentage obtained dividing the number of higher than 80% coverage reports on CodeClimate by the number of total CodeClimate reports for the requested period.
``` json
{
  "PERCENTAGE_CC_COVERAGEOVER80_CC_COVERAGE": {
    "computer": {
      "$ref": "#/context/definitions/computers/eventcomputer"
    },
    "metric": {
      "computing": "actual",
      "element": {
        "percentage": {
          "related": {
            "codeclimate": {
              "coverage": {
                "data": {
                  "attributes": {
                    "covered_percent": "%HIGHER%80"
                  }
                }
              }
            },
            "window": 86400
          }
        }
      },
      "event": {
        "codeclimate": {
          "coverage": {
            "data": {
              "attributes": {
                "covered_percent": "%HIGHER_OR_EQUAL%0"
              }
            }
          }
        }
      },
      "scope": {
        "$ref": "#/context/definitions/scopes/development"
      }
    }
  }
}
```

# Guarantees

### 75_PERCENT_NEWBRANCH_STARTED_STORIES_WITHIN_A_DAY_WRAPPER
At least 75% of started stories must match a creation of a branch within a day.
``` json
{
  "id": "75_PERCENT_NEWBRANCH_STARTED_STORIES_WITHIN_A_DAY_WRAPPER",
  "notes": "### Description\r\n```\r\nTP-1: At least 75% of started stories(PT) must match a creation of a branch (GH) within a day.",
  "description": "At least 75% of started stories must match a creation of a branch within a day.",
  "scope": {
    "$ref": "#/context/definitions/scopes/development"
  },
  "of": [
    {
      "scope": {
        "project": "1010101010"
      },
      "objective": "PERCENTAGE_GHWR_NEWBRANCH_PT_STARTEDSTORIES >= 75",
      "with": {
        "PERCENTAGE_GHWR_NEWBRANCH_PT_STARTEDSTORIES": {}
      },
      "window": {
        "type": "static",
        "period": "daily",
        "initial": "2018-01-01"
      }
    }
  ]
}
```

### 75_PERCENT_NEWBRANCH_STARTED_STORIES_WITHIN_A_DAY
At least 75% of started stories must match a creation of a branch within a day.
``` json
{
  "id": "75_PERCENT_NEWBRANCH_STARTED_STORIES_WITHIN_A_DAY",
  "notes": "### Description\r\n```\r\nTP-1: At least 75% of started stories(PT) must match a creation of a branch (GH) within a day.",
  "description": "At least 75% of started stories must match a creation of a branch within a day.",
  "scope": {
    "$ref": "#/context/definitions/scopes/development"
  },
  "of": [
    {
      "scope": {
        "project": "1010101010"
      },
      "objective": "PERCENTAGE_GH_NEWBRANCH_PT_STARTEDSTORIES >= 75",
      "with": {
        "PERCENTAGE_GH_NEWBRANCH_PT_STARTEDSTORIES": {}
      },
      "window": {
        "type": "static",
        "period": "daily",
        "initial": "2018-01-01"
      }
    }
  ]
}
```

### 75_PERCENT_NEWBRANCH_STARTED_STORIES_WITHIN_A_DAY_BIND
At least 75% of started stories must match a creation of a branch within a day.
``` json
{
  "id": "75_PERCENT_NEWBRANCH_STARTED_STORIES_WITHIN_A_DAY_BIND",
  "notes": "### Description\r\n```\r\nTP-1: At least 75% of started stories(PT) must match a creation of a branch (GH) within a day.",
  "description": "At least 75% of started stories must match a creation of a branch within a day.",
  "scope": {
    "$ref": "#/context/definitions/scopes/development"
  },
  "of": [
    {
      "scope": {
        "project": "1010101010"
      },
      "objective": "PERCENTAGE_GH_NEWBRANCH_PT_STARTEDSTORIES_BIND >= 75",
      "with": {
        "PERCENTAGE_GH_NEWBRANCH_PT_STARTEDSTORIES_BIND": {}
      },
      "window": {
        "type": "static",
        "period": "daily",
        "initial": "2018-01-01"
      }
    }
  ]
}
```

### 75_PERCENT_MASTER_PR_OPEN_FINSH_STORIES_WITHIN_A_DAY
At least 75% of finished stories must match the creation of a PR within a day.
``` json
{
  "id": "75_PERCENT_MASTER_PR_OPEN_FINSH_STORIES_WITHIN_A_DAY",
  "notes": "### Description\r\n```\r\nTP-1: At least 75% of finished stories(PT) must match creation of a PR within a day.",
  "description": "At least 75% of finished stories must match the creation of a PR within a day.",
  "scope": {
    "$ref": "#/context/definitions/scopes/development"
  },
  "of": [
    {
      "scope": {
        "project": "1010101010"
      },
      "objective": "PERCENTAGE_GH_OPENPR_PT_FINISHEDSTORIES >= 75",
      "with": {
        "PERCENTAGE_GH_OPENPR_PT_FINISHEDSTORIES": {}
      },
      "window": {
        "type": "static",
        "period": "daily",
        "initial": "2018-01-01"
      }
    }
  ]
}
```

### 75_PERCENT_MASTER_PR_OPEN_FINSH_STORIES_WITHIN_A_DAY_BIND
At least 75% of finished stories must match the creation of a PR within a day.
``` json
{
  "id": "75_PERCENT_MASTER_PR_OPEN_FINSH_STORIES_WITHIN_A_DAY_BIND",
  "notes": "### Description\r\n```\r\nTP-1: At least 75% of finished stories(PT) must match creation of a PR within a day.",
  "description": "At least 75% of finished stories must match the creation of a PR within a day.",
  "scope": {
    "$ref": "#/context/definitions/scopes/development"
  },
  "of": [
    {
      "scope": {
        "project": "1010101010"
      },
      "objective": "PERCENTAGE_GH_OPENPR_PT_FINISHEDSTORIES_BIND >= 75",
      "with": {
        "PERCENTAGE_GH_OPENPR_PT_FINISHEDSTORIES_BIND": {}
      },
      "window": {
        "type": "static",
        "period": "daily",
        "initial": "2018-01-01"
      }
    }
  ]
}
```

### 75_PERCENT_MASTER_PR_MERGE_DELVR_STORIES_WITHIN_A_DAY
At least 75% of delivered stories must match the merge of a PR into master within a day.
``` json
{
  "id": "75_PERCENT_MASTER_PR_MERGE_DELVR_STORIES_WITHIN_A_DAY",
  "notes": "### Description\r\n```\r\nTP-1: At least 75% of delivered stories(PT) must match a the merge of a PR into master within a day.",
  "description": "At least 75% of delivered stories must match the merge of a PR into master within a day.",
  "scope": {
    "$ref": "#/context/definitions/scopes/development"
  },
  "of": [
    {
      "scope": {
        "project": "1010101010"
      },
      "objective": "PERCENTAGE_GH_MERGEPR_PT_DELIVEREDSTORIES >= 75",
      "with": {
        "PERCENTAGE_GH_MERGEPR_PT_DELIVEREDSTORIES": {}
      },
      "window": {
        "type": "static",
        "period": "daily",
        "initial": "2018-01-01"
      }
    }
  ]
}
```

### 75_PERCENT_MASTER_PR_MERGE_DELVR_STORIES_WITHIN_A_DAY_BIND
At least 75% of delivered stories must match the merge of a PR into master within a day.
``` json
{
  "id": "75_PERCENT_MASTER_PR_MERGE_DELVR_STORIES_WITHIN_A_DAY_BIND",
  "notes": "### Description\r\n```\r\nTP-1: At least 75% of delivered stories(PT) must match a the merge of a PR into master within a day.",
  "description": "At least 75% of delivered stories must match the merge of a PR into master within a day.",
  "scope": {
    "$ref": "#/context/definitions/scopes/development"
  },
  "of": [
    {
      "scope": {
        "project": "1010101010"
      },
      "objective": "PERCENTAGE_GH_MERGEPR_PT_DELIVEREDSTORIES_BIND >= 75",
      "with": {
        "PERCENTAGE_GH_MERGEPR_PT_DELIVEREDSTORIES_BIND": {}
      },
      "window": {
        "type": "static",
        "period": "daily",
        "initial": "2018-01-01"
      }
    }
  ]
}
```

### 75_PERCENT_MASTER_PR_MERGE_DEPLOY_WITHIN_A_DAY
At least 75% of delivered stories must match the merge of a PR into master within a day.
``` json
{
  "id": "75_PERCENT_MASTER_PR_MERGE_DEPLOY_WITHIN_A_DAY",
  "notes": "### Description\r\n```\r\nTP-1: At least 75% of delivered stories(PT) must match a the merge of a PR into master within a day.",
  "description": "At least 75% of delivered stories must match the merge of a PR into master within a day.",
  "scope": {
    "$ref": "#/context/definitions/scopes/development"
  },
  "of": [
    {
      "scope": {
        "project": "1010101010"
      },
      "objective": "PERCENTAGE_HE_RELEASES_PT_DELIVEREDSTORIES >= 75",
      "with": {
        "PERCENTAGE_HE_RELEASES_PT_DELIVEREDSTORIES": {}
      },
      "window": {
        "type": "static",
        "period": "daily",
        "initial": "2018-01-01"
      }
    }
  ]
}
```

### 75_PERCENT_MASTER_PR_MERGE_DEPLOY_WITHIN_A_DAY_BIND
At least 75% of delivered stories must match the merge of a PR into master within a day.
``` json
{
  "id": "75_PERCENT_MASTER_PR_MERGE_DEPLOY_WITHIN_A_DAY_BIND",
  "notes": "### Description\r\n```\r\nTP-1: At least 75% of delivered stories(PT) must match a the merge of a PR into master within a day.",
  "description": "At least 75% of delivered stories must match the merge of a PR into master within a day.",
  "scope": {
    "$ref": "#/context/definitions/scopes/development"
  },
  "of": [
    {
      "scope": {
        "project": "1010101010"
      },
      "objective": "PERCENTAGE_HE_RELEASES_PT_DELIVEREDSTORIES_BIND >= 75",
      "with": {
        "PERCENTAGE_HE_RELEASES_PT_DELIVEREDSTORIES_BIND": {}
      },
      "window": {
        "type": "static",
        "period": "daily",
        "initial": "2018-01-01"
      }
    }
  ]
}
```

### COVERAGE_DELTA_VARIATION_HIGHER_EQUAL_ZERO
This returns the delta variation of the coverage. The points values should be greater than 0.
``` json
{
  "id": "COVERAGE_DELTA_VARIATION_HIGHER_EQUAL_ZERO",
  "notes": "### Description\r\n```\r\n: The delta variation of the coverage must be higher than 0.",
  "description": "This returns the delta variation of the coverage. The points values should be greater than 0.",
  "scope": {
    "$ref": "#/context/definitions/scopes/development"
  },
  "of": [
    {
      "scope": {
        "project": "1010101010"
      },
      "objective": "VALUE_CC_COVERAGE - VALUE_CC_COVERAGE_OFFSET >= 0",
      "with": {
        "VALUE_CC_COVERAGE": {},
        "VALUE_CC_COVERAGE_OFFSET": {}
      },
      "window": {
        "type": "static",
        "period": "daily",
        "initial": "2018-01-01"
      }
    }
  ]
}
```

