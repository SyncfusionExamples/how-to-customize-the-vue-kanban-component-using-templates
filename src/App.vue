<template>
    <ejs-kanban id="kanban" cssClass="kanban-header-template" keyField="Status" :dataSource="data"
        :cardSettings="cardSettings" :swimlaneSettings="swimlaneSettings">
        <e-columns>
            <e-column headerText="To Do" keyField="Open" :template="'columnsTemplate'">
            </e-column>
            <e-column headerText="In Progress" keyField="InProgress" :template="'columnsTemplate'">
            </e-column>
            <e-column headerText="In Review" keyField="Review" :template="'columnsTemplate'">
            </e-column>
            <e-column headerText="Done" keyField="Close" :template="'columnsTemplate'">
            </e-column>
        </e-columns>
        <template #columnsTemplate="{data}">
            <div class="header-template-wrap">
                <div :class="getClassName(data)"></div>
                <div class="header-text">{{ data.headerText }}</div>
            </div>
        </template>
        <template #swimlaneTemplate="{data}">
        <div class="swimlane-template">
            <div>
                <img :src="getImageSource(data)" :alt="data.keyField"/>
                <span>{{ data.textField }}</span>
            </div>
        </div></template>
        <template #cardTemplate="{data}">
        <div class="e-card-content">
            <table class="card-template-wrap">
                <tbody>
                    <tr>
                        <td class="CardHeader"><span class="bolded">Id:</span>{{ data.Id }}</td>
                    </tr>
                    <tr>
                        <td class="CardHeader"> <span class="bolded">Type:</span>{{ data.Type }}</td>
                    </tr>
                    <tr>
                        <td class="CardHeader"><span class="bolded">Priority:</span> {{ data.Priority }}</td>
                    </tr>
                    <tr>
                        <td class="CardHeader"><span class="bolded">Summary:</span> {{ data.Summary }}</td>
                    </tr>
                </tbody>
            </table>
        </div></template>
    </ejs-kanban>
</template>
<script>

import { KanbanComponent, ColumnsDirective, ColumnDirective } from "@syncfusion/ej2-vue-kanban";
export default {
    components: {
        "ejs-kanban": KanbanComponent,
        "e-columns": ColumnsDirective,
        "e-column": ColumnDirective,
    },
    data: function () {
        return {
            data: [
                {
                    "Id": "Task 1",
                    "Title": "Task - 29001",
                    "Status": "Open",
                    "Summary": "Analyze the new requirements gathered from the customer.",
                    "Type": "Story",
                    "Priority": "Low",
                    "Tags": "Analyze,Customer",
                    "Estimate": 3.5,
                    "Assignee": "Nancy Davloio",
                    "RankId": 1,
                    "Color": "#02897B",
                    "ClassName": "e-story, e-low, e-nancy-davloio"
                },
                {
                    "Id": "Task 2",
                    "Title": "Task - 29002",
                    "Status": "InProgress",
                    "Summary": "Improve application performance",
                    "Type": "Improvement",
                    "Priority": "Normal",
                    "Tags": "Improvement",
                    "Estimate": 6,
                    "Assignee": "Andrew Fuller",
                    "RankId": 1,
                    "Color": "#673AB8",
                    "ClassName": "e-improvement, e-normal, e-andrew-fuller"
                },
                {
                    "Id": "Task 3",
                    "Title": "Task - 29003",
                    "Status": "Open",
                    "Summary": "Arrange a web meeting with the customer to get new requirements.",
                    "Type": "Others",
                    "Priority": "Critical",
                    "Tags": "Meeting",
                    "Estimate": 5.5,
                    "Assignee": "Janet Leverling",
                    "RankId": 2,
                    "Color": "#1F88E5",
                    "ClassName": "e-others, e-critical, e-janet-leverling"
                },
                {
                    "Id": "Task 4",
                    "Title": "Task - 29004",
                    "Status": "InProgress",
                    "Summary": "Fix the issues reported in the IE browser.",
                    "Type": "Bug",
                    "Priority": "Critical",
                    "Tags": "IE",
                    "Estimate": 2.5,
                    "Assignee": "Janet Leverling",
                    "RankId": 2,
                    "Color": "#E64A19",
                    "ClassName": "e-bug, e-release, e-janet-leverling"
                },
                {
                    "Id": "Task 5",
                    "Title": "Task - 29005",
                    "Status": "Review",
                    "Summary": "Fix the issues reported by the customer.",
                    "Type": "Bug",
                    "Priority": "Low",
                    "Tags": "Customer",
                    "Estimate": "3.5",
                    "Assignee": "Steven walker",
                    "RankId": 1,
                    "Color": "#E64A19",
                    "ClassName": "e-bug, e-low, e-steven-walker"
                },
                {
                    "Id": "Task 6",
                    "Title": "Task - 29007",
                    "Status": "Validate",
                    "Summary": "Validate new requirements",
                    "Type": "Improvement",
                    "Priority": "Low",
                    "Tags": "Validation",
                    "Estimate": 1.5,
                    "Assignee": "Robert King",
                    "RankId": 1,
                    "Color": "#673AB8",
                    "ClassName": "e-improvement, e-low, e-robert-king"
                },
                {
                    "Id": "Task 7",
                    "Title": "Task - 29009",
                    "Status": "Review",
                    "Summary": "Fix the issues reported in Safari browser.",
                    "Type": "Bug",
                    "Priority": "Critical",
                    "Tags": "Fix,Safari",
                    "Estimate": 1.5,
                    "Assignee": "Nancy Davloio",
                    "RankId": 2,
                    "Color": "#E64A19",
                    "ClassName": "e-bug, e-release, e-nancy-davloio"
                },
                {
                    "Id": "Task 8",
                    "Title": "Task - 29010",
                    "Status": "Close",
                    "Summary": "Test the application in the IE browser.",
                    "Type": "Story",
                    "Priority": "Low",
                    "Tags": "Review,IE",
                    "Estimate": 5.5,
                    "Assignee": "Margaret hamilt",
                    "RankId": 3,
                    "Color": "#02897B",
                    "ClassName": "e-story, e-low, e-margaret-hamilt"
                },
                {
                    "Id": "Task 9",
                    "Title": "Task - 29011",
                    "Status": "Validate",
                    "Summary": "Validate the issues reported by the customer.",
                    "Type": "Story",
                    "Priority": "High",
                    "Tags": "Validation,Fix",
                    "Estimate": 1,
                    "Assignee": "Steven walker",
                    "RankId": 1,
                    "Color": "#02897B",
                    "ClassName": "e-story, e-high, e-steven-walker"
                },
                {
                    "Id": "Task 10",
                    "Title": "Task - 29015",
                    "Status": "Open",
                    "Summary": "Show the retrieved data from the server in grid control.",
                    "Type": "Story",
                    "Priority": "High",
                    "Tags": "Database,SQL",
                    "Estimate": 5.5,
                    "Assignee": "Margaret hamilt",
                    "RankId": 4,
                    "Color": "#02897B",
                    "ClassName": "e-story, e-high, e-margaret-hamilt"
                },
                {
                    "Id": "Task 11",
                    "Title": "Task - 29016",
                    "Status": "InProgress",
                    "Summary": "Fix cannot open user’s default database SQL error.",
                    "Priority": "Critical",
                    "Type": "Bug",
                    "Tags": "Database,Sql2008",
                    "Estimate": 2.5,
                    "Assignee": "Janet Leverling",
                    "RankId": 4,
                    "Color": "#E64A19",
                    "ClassName": "e-bug, e-critical, e-janet-leverling"
                },
                {
                    "Id": "Task 12",
                    "Title": "Task - 29017",
                    "Status": "Review",
                    "Summary": "Fix the issues reported in data binding.",
                    "Type": "Story",
                    "Priority": "Normal",
                    "Tags": "Databinding",
                    "Estimate": "3.5",
                    "Assignee": "Janet Leverling",
                    "RankId": 4,
                    "Color": "#02897B",
                    "ClassName": "e-story, e-normal, e-janet-leverling"
                },
                {
                    "Id": "Task 13",
                    "Title": "Task - 29018",
                    "Status": "Close",
                    "Summary": "Analyze SQL server 2008 connection.",
                    "Type": "Story",
                    "Priority": "Critical",
                    "Tags": "Grid,Sql",
                    "Estimate": 2,
                    "Assignee": "Andrew Fuller",
                    "RankId": 4,
                    "Color": "#02897B",
                    "ClassName": "e-story, e-release, e-andrew-fuller"
                },
                {
                    "Id": "Task 14",
                    "Title": "Task - 29019",
                    "Status": "Validate",
                    "Summary": "Validate databinding issues.",
                    "Type": "Story",
                    "Priority": "Low",
                    "Tags": "Validation",
                    "Estimate": 1.5,
                    "Assignee": "Margaret hamilt",
                    "RankId": 1,
                    "Color": "#02897B",
                    "ClassName": "e-story, e-low, e-margaret-hamilt"
                },
                {
                    "Id": "Task 15",
                    "Title": "Task - 29020",
                    "Status": "Close",
                    "Summary": "Analyze grid control.",
                    "Type": "Story",
                    "Priority": "High",
                    "Tags": "Analyze",
                    "Estimate": 2.5,
                    "Assignee": "Margaret hamilt",
                    "RankId": 5,
                    "Color": "#02897B",
                    "ClassName": "e-story, e-high, e-margaret-hamilt"
                },
                {
                    "Id": "Task 16",
                    "Title": "Task - 29021",
                    "Status": "Close",
                    "Summary": "Stored procedure for initial data binding of the grid.",
                    "Type": "Others",
                    "Priority": "Critical",
                    "Tags": "Databinding",
                    "Estimate": 1.5,
                    "Assignee": "Steven walker",
                    "RankId": 6,
                    "Color": "#1F88E5",
                    "ClassName": "e-others, e-release, e-steven-walker"
                },
                {
                    "Id": "Task 17",
                    "Title": "Task - 29022",
                    "Status": "Close",
                    "Summary": "Analyze stored procedures.",
                    "Type": "Story",
                    "Priority": "Critical",
                    "Tags": "Procedures",
                    "Estimate": 5.5,
                    "Assignee": "Janet Leverling",
                    "RankId": 7,
                    "Color": "#02897B",
                    "ClassName": "e-story, e-release, e-janet-leverling"
                },
                {
                    "Id": "Task 18",
                    "Title": "Task - 29023",
                    "Status": "Validate",
                    "Summary": "Validate editing issues.",
                    "Type": "Story",
                    "Priority": "Critical",
                    "Tags": "Editing",
                    "Estimate": 1,
                    "Assignee": "Nancy Davloio",
                    "RankId": 1,
                    "Color": "#02897B",
                    "ClassName": "e-story, e-critical, e-nancy-davloio"
                },
                {
                    "Id": "Task 19",
                    "Title": "Task - 29024",
                    "Status": "Review",
                    "Summary": "Test editing functionality.",
                    "Type": "Story",
                    "Priority": "Normal",
                    "Tags": "Editing,Test",
                    "Estimate": 0.5,
                    "Assignee": "Nancy Davloio",
                    "RankId": 5,
                    "Color": "#02897B",
                    "ClassName": "e-story, e-normal, e-nancy-davloio"
                },
                {
                    "Id": "Task 20",
                    "Title": "Task - 29025",
                    "Status": "Open",
                    "Summary": "Enhance editing functionality.",
                    "Type": "Improvement",
                    "Priority": "Low",
                    "Tags": "Editing",
                    "Estimate": 3.5,
                    "Assignee": "Andrew Fuller",
                    "RankId": 5,
                    "Color": "#673AB8",
                    "ClassName": "e-improvement, e-low, e-andrew-fuller"
                },
                {
                    "Id": "Task 21",
                    "Title": "Task - 29026",
                    "Status": "InProgress",
                    "Summary": "Improve the performance of the editing functionality.",
                    "Type": "Epic",
                    "Priority": "High",
                    "Tags": "Performance",
                    "Estimate": 6,
                    "Assignee": "Nancy Davloio",
                    "RankId": 5,
                    "Color": "#e91e64",
                    "ClassName": "e-epic, e-high, e-nancy-davloio"
                },
                {
                    "Id": "Task 22",
                    "Title": "Task - 29027",
                    "Status": "Open",
                    "Summary": "Arrange web meeting with the customer to show editing demo.",
                    "Type": "Others",
                    "Priority": "High",
                    "Tags": "Meeting,Editing",
                    "Estimate": 5.5,
                    "Assignee": "Steven walker",
                    "RankId": 6,
                    "Color": "#1F88E5",
                    "ClassName": "e-others, e-high, e-steven-walker"
                },
                {
                    "Id": "Task 23",
                    "Title": "Task - 29029",
                    "Status": "Review",
                    "Summary": "Fix the editing issues reported by the customer.",
                    "Type": "Bug",
                    "Priority": "Low",
                    "Tags": "Editing,Fix",
                    "Estimate": "3.5",
                    "Assignee": "Janet Leverling",
                    "RankId": 6,
                    "Color": "#E64A19",
                    "ClassName": "e-bug, e-low, e-janet-leverling"
                },
                {
                    "Id": "Task 24",
                    "Title": "Task - 29030",
                    "Status": "Testing",
                    "Summary": "Fix the issues reported by the customer.",
                    "Type": "Bug",
                    "Priority": "Critical",
                    "Tags": "Customer",
                    "Estimate": "3.5",
                    "Assignee": "Steven walker",
                    "RankId": 1,
                    "Color": "#E64A19",
                    "ClassName": "e-bug, e-critical, e-steven-walker"
                },
                {
                    "Id": "Task 25",
                    "Title": "Task - 29031",
                    "Status": "Testing",
                    "Summary": "Fix the issues reported in Safari browser.",
                    "Type": "Bug",
                    "Priority": "Critical",
                    "Tags": "Fix,Safari",
                    "Estimate": 1.5,
                    "Assignee": "Nancy Davloio",
                    "RankId": 2,
                    "Color": "#E64A19",
                    "ClassName": "e-bug, e-release, e-nancy-davloio"
                },
                {
                    "Id": "Task 26",
                    "Title": "Task - 29032",
                    "Status": "Testing",
                    "Summary": "Check Login page validation.",
                    "Type": "Story",
                    "Priority": "Critical",
                    "Tags": "Testing",
                    "Estimate": 0.5,
                    "Assignee": "Michael Suyama",
                    "RankId": 3,
                    "Color": "#02897B",
                    "ClassName": "e-story, e-release, e-michael-suyama"
                },
                {
                    "Id": "Task 27",
                    "Title": "Task - 29033",
                    "Status": "Testing",
                    "Summary": "Fix the issues reported in data binding.",
                    "Type": "Story",
                    "Priority": "Normal",
                    "Tags": "Databinding",
                    "Estimate": "3.5",
                    "Assignee": "Janet Leverling",
                    "RankId": 4,
                    "Color": "#02897B",
                    "ClassName": "e-story, e-normal, e-janet-leverling"
                },
                {
                    "Id": "Task 28",
                    "Title": "Task - 29034",
                    "Status": "Testing",
                    "Summary": "Test editing functionality.",
                    "Type": "Story",
                    "Priority": "Normal",
                    "Tags": "Editing,Test",
                    "Estimate": 0.5,
                    "Assignee": "Nancy Davloio",
                    "RankId": 5,
                    "Color": "#02897B",
                    "ClassName": "e-story, e-normal, e-nancy-davloio"
                },
                {
                    "Id": "Task 29",
                    "Title": "Task - 29035",
                    "Status": "Testing",
                    "Summary": "Fix editing issues reported in Firefox.",
                    "Type": "Bug",
                    "Priority": "Critical",
                    "Tags": "Editing,Fix",
                    "Estimate": 1.5,
                    "Assignee": "Robert King",
                    "RankId": 7,
                    "Color": "#E64A19",
                    "ClassName": "e-bug, e-critical, e-robert-king"
                },
                {
                    "Id": "Task 30",
                    "Title": "Task - 29036",
                    "Status": "Testing",
                    "Summary": "Test editing feature in the IE browser.",
                    "Type": "Story",
                    "Priority": "Normal",
                    "Tags": "Testing",
                    "Estimate": 5.5,
                    "Assignee": "Janet Leverling",
                    "RankId": 10,
                    "Color": "#02897B",
                    "ClassName": "e-story, e-normal, e-janet-leverling"
                }
            ],
            cardSettings: {
                contentField: "Summary",
                headerField: "Id",
                template: "cardTemplate"
            },
            swimlaneSettings: {
                keyField: "Assignee",
                template: "swimlaneTemplate"
            }
        }
    },
    methods:{
        getClassName: function(data){
            return "header-icon e-icons "+ data.keyField;
        },
        getImageSource: function(data){
            return "src/assets/images/"+ data.keyField + ".png";
        }
    }
}
</script>

<style>
@import '../node_modules/@syncfusion/ej2-base/styles/material.css';
@import '../node_modules/@syncfusion/ej2-buttons/styles/material.css';
@import '../node_modules/@syncfusion/ej2-layouts/styles/material.css';
@import '../node_modules/@syncfusion/ej2-dropdowns/styles/material.css';
@import '../node_modules/@syncfusion/ej2-inputs/styles/material.css';
@import '../node_modules/@syncfusion/ej2-navigations/styles/material.css';
@import '../node_modules/@syncfusion/ej2-popups/styles/material.css';
@import '../node_modules/@syncfusion/ej2-vue-kanban/styles/material.css';

.kanban-header-template.e-kanban .header-template-wrap {
    display: inline-flex;
    font-size: 15px;
    font-weight: 400;
}

.kanban-header-template.e-kanban .header-template-wrap .header-icon {
    font-family: 'Kanban priority icons';
    margin-top: 3px;
    width: 10%;
}

.kanban-header-template.e-kanban .header-template-wrap .header-text {
    margin-left: 15px;
}

.kanban-header-template.e-kanban.e-rtl .header-template-wrap .header-text {
    margin-right: 15px;
}

.kanban-header-template.e-kanban .card-header {
    padding-left: 12px;
}

.kanban-header-template.e-kanban .Open::before {
    content: '\e700';
    color: #0251cc;
    font-size: 16px;
}

.kanban-header-template.e-kanban .InProgress::before {
    content: '\e703';
    color: #ea9713;
    font-size: 16px;
}

.kanban-header-template.e-kanban .Review::before {
    content: '\e701';
    color: #8e4399;
    font-size: 16px;
}

.kanban-header-template.e-kanban .Close::before {
    content: '\e702';
    color: #63ba3c;
    font-size: 16px;
}

@font-face {
    font-family: 'Kanban priority icons';
    src:
        url(data:application/x-font-ttf;charset=utf-8;base64,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) format('truetype');
    font-weight: normal;
    font-style: normal;
}

[class^="sf-icon-"],
[class*=" sf-icon-"] {
    font-family: 'Kanban priority icons' !important;
    font-size: 55px;
    font-style: normal;
    font-weight: normal;
    font-variant: normal;
    text-transform: none;
    line-height: 1;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
}

.swimlane-template {
    display: inline-block;
    font-size: 18px;
    font-weight: 500;
}
.swimlane-template img {
    height: 24px;
    width: 24px;
    border-radius: 50%;
}
.swimlane-template span {
    padding-left: 5px;
    vertical-align: top;
}
.e-kanban .e-kanban-content .e-content-row.e-swimlane-row .e-content-cells .e-swimlane-header .e-item-count {
    padding: 4px;
}

.e-kanban .card-template-wrap td {
    background: none !important;
}

.e-kanban .card-template-wrap .CardHeader {
    font-weight: 500;
    text-align: left !important;
}
.bolded {
    font-weight: bold;
}
</style>