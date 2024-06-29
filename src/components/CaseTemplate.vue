<template>
    <div class="case">
        <div class="case-title">
          <slot name="caseName"></slot>
            | 本例参阅：
            <slot name="caseInfo"></slot>
        </div>
        <div>
            涉及API:
            <slot name="apiInfo"></slot>
        </div>
        <div>
            <div>Demo:</div>
            <slot></slot>
        </div>
    </div>
  </template>
  
  <style scoped>
  
  </style>
  