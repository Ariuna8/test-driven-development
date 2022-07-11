# test-driven-development
1. Initialize project:
npm init @vitejs/app
choose vanilla
2. Add testing framework:
npm install jest
3. Create file  in main:
stack.test.js
4. In package.json set up new script:
"test": "jest --watchAll --verbose --coverage"
5. Add types of the project(optional):
npm install @types/jest
6. Create in test directory:
jsconfig.json
7. In jsconfig.json type:
   {
   "typeAcquisition": {
   "include": [
   "jest"
   ]
   }
   }
8. Wallaby(allows watch pass/fail tests right in editor)
9. Write test:
   class Stack {
   constructor() {
   this.top = -1
   this.items = {}
   }
   get peek(){
   return this.items[this.top]
   }
   push(value) {
   this.top += 1
   this.items[this.top] = value
   }
   }   

describe('my stack', () => {
let stack
beforeEach(() => {
stack = new Stack()
})

it('is created empty', () => {
const stack = new Stack()
expect(stack.top).toBe(-1)
expect(stack.items).toEqual({})
})

it('can push to the top', () => {
stack.push('🥑 ')
expect(stack.top).toBe(0)
expect(stack.peek).toBe('🥑 ')
})
})
