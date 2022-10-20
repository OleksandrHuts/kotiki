<template>
    <div :class="{'hasError': isError}">
        <Button></Button>
        <img class="user_image" :src="userPhoto"   >
        <p>{{ username }}</p>
        <input @change="updateNameInParent" v-model="username" type="text" placeholder="Add name" />
        <span v-show="isError" class="error">{{ errorText }}</span>
        <Button>
            <template #label>Sent</template>
            <template #image>
                <img class="icon" src="https://cdn2.iconfinder.com/data/icons/font-awesome/1792/phone-512.png" alt="">
            </template>
        </Button>
    </div>
</template>

<script>
import Button from '@/components/Button/Button.vue';

    export default {
    name: "UserCard",
    components: { Button },
    data() {
        return {
            username: "Vlad",
            isError: false
        };
    },
    props: {
        userPhoto: {
            type: String,
            default: ""
        }
    },
    methods: {
        updateNameInParent() {
            this.$emit("getUserName", this.username);
        },
        showInfo() {
            console.log("Info from user card", this.username);
        }
    },
    watch: {
        username(val, oldVal) {
            if (val != oldVal) {
                if (val.length <= 3) {
                    this.isError = true;
                }
                else if (val.length >= 10) {
                    this.isError = true;
                }
                else {
                    this.isError = false;
                }
            }
        }
    },
    computed: {
        errorText() {
            let text = "";
            if (this.username.length <= 3) {
                text = "Too short username";
            }
            else if (this.username.length >= 10) {
                text = "Too long username";
            }
            else {
                text = "";
            }
            return text;
        },
        parentErrorClass() {
            return this.isError ? "hasError" : "noError";
        }
    },
}
</script>

<style scoped lang="scss" src="./style.scss"></style>