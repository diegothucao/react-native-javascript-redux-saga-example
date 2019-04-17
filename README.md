# react-native-javascript-redux-saga-example
This is an essential example to build react-native app using Javascript and Redux Saga

Step to run
1. Checkout this respo
2. `yarn install` OR `npm install`
3. `react-native eject`
4. `react-native run-ios` OR `react-native run-android`

if you see any issue, please do not hesitate to create an issue here or can contact me via email: cao.trung.thu@gmail.com or https://www.linkedin.com/in/diegothucao/

Define Actions 

```javascript 

import { FETCHING_DEALS_LIST, FETCHING_DEALS_SEARCH, VIEW_DEAL_DETAIL, BACK_TO_DEAL_LIST, FETCHING_DEAL_DETAIL } from "../util/constants";

export const fetchData = () => {
    return { type: FETCHING_DEALS_LIST } 
}

export const searchDeals = (searchStr) => {
    return { type: FETCHING_DEALS_SEARCH, payload: searchStr } 
}

export const fetchDetail = (dealId) => {
    return { type: FETCHING_DEAL_DETAIL, payload: dealId }
}

export const backToDealList = () => {
    return { type: BACK_TO_DEAL_LIST } 
}
```

Define Reducer 

```javascript
import {
        FETCHING_DEALS_LIST, FETCHING_DEALS_SUCCESS, FETCHING_DEALS_FAIL
        , FETCHING_DEALS_SEARCH, BACK_TO_DEAL_LIST,
        FETCHING_DEAL_DETAIL, FETCHING_DEAL_DETAIL_SUCCESS, FETCHING_DEAL_DETAIL_FAIL
} from '../util/constants'

const initialState = {
        data: [],
        currentDealId: null,
        currentDeal: null,
        dataFetched: false,
        isFetching: false,
        error: false
}

export default dataReducer = (state = initialState, action) => {
        switch (action.type) {
                case FETCHING_DEALS_LIST:
                        return {
                                ...state,
                                data: [],
                                isFetching: true
                        }
                case FETCHING_DEALS_SEARCH:
                        return {
                                ...state,
                                data: [],
                                isFetching: true
                        }
                case FETCHING_DEALS_SUCCESS:
                        return {
                                ...state,
                                isFetching: false,
                                data: action.data
                        }
                case FETCHING_DEALS_FAIL:
                        return {
                                ...state,
                                isFetching: false,
                                error: true
                        }
                case FETCHING_DEAL_DETAIL:
                        return {
                                ...state,
                                isFetching: true,
                                currentDeal: null
                        }
                case FETCHING_DEAL_DETAIL_SUCCESS:
                        return {
                                ...state,
                                isFetching: false,
                                currentDeal: action.data
                        }
                case FETCHING_DEAL_DETAIL_FAIL:
                        return {
                                ...state,
                                isFetching: false,
                                error: true
                        }
                case BACK_TO_DEAL_LIST:
                        return {
                                ...state,
                                isFetching: false,
                                currentDeal: null
                        }
                default:
                        return state
        }
}
```

Give me A STAR if you see it is helpful for you.

Thanks

references
1. https://facebook.github.io/react-native/docs/tutorial
2. https://github.com/jscomplete/react-native-essential-training
3. https://redux-saga.js.org
4. https://www.tutorialspoint.com/es6
