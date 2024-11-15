<script>
import PictureInput from "vue-picture-input"
export default {
    data() {
        return {
            wordSearchImg: null
        }
    },

    methods: {
        onChange(e) {
            this.wordSearchImg = e.target.files[0]
        },
        submitForm() {
            console.log("Data submitted")
        }
    },

    components: {
        PictureInput
    }
}
</script>

<template>
    <div class="wrapper">
        <div class="form-container">
            <div class="form-title">
                <h1>Word Search Solver App</h1>
            </div>

            <form @submit.prevent="submitForm">
            <div class="picture-input-container">
                <picture-input 
                ref="wordSearchInput"
                width="400" 
                height="400" 
                margin="16" 
                accept="image/jpeg,image/png" 
                size="10" 
                button-class="btn"
                :custom-strings="{
                    upload: '<h1>Your device does not support file uploading. Sorry!</h1>',
                    drag: 'Drag word search image 📝'
                }"
                @change="onChange">
                </picture-input>
            </div>

                <label for="word-search-text-area">Enter words you want to find (Seperated by comma): </label>
                <textarea name="word-search-text-area" id="" cols="50" rows="10"></textarea>
                
                <div class="submit-btn">
                    <button type="submit">Submit</button>
                </div>
            </form>
        </div>
    </div>
</template>

<style>
    *,
    ::before,
    ::after {
        box-sizing: border-box;
        margin: 0;
        padding: 0;
    }
    .wrapper {
        display: flex;
        justify-content: center;
        align-items: center;
        min-height: 100vh;
        background-color: #f8f8f8;
    }
    h1 {
        text-align: center;
    }
    .picture-input-container {
        margin: 20px 0px;
    }
    .form-title {
        margin: 20px 0px;
    }
    label {
        text-align: center;
        margin-bottom: 10px;
        display: block;
    }
    textarea {
        display: block;
    }
    .submit-btn {
        display: flex;
        justify-content: center;
    }
    button {
        font-size: 16px;
        margin: 25px;
        padding: 14px 50px;
    }
</style>