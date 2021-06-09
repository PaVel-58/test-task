<template>
    <div class="wrapper" :class="{scroll: showPopup}">
        <BigButton 
            text="Налоговый вычет" 
            light 
            @click="showPopup = true"
        />
        <pPopup 
            v-if="showPopup"
            @closePopup="showPopup = false"
        >
            <div>
                <h2 class="popup-title">Налоговый вычет</h2>
                <p class="popup-discription">
                    Используйте налоговый вычет чтобы погасить ипотеку досрочно. Размер налогового вычета состовляет не более 13% от своего официального годового дохода.
                </p>
                <pInput 
                    label="Ваша зарплата в месяц" 
                    placeholder="Введите данные" 
                    @getValue="value => {inputValue = value}"
                />
                <div class="mb-24 mt-8">
                    <TextButton 
                        text="Рассчитать"
                        @click="сalculate()" 
                    />
                </div>
                <pList v-if="result != ''" :listsItems="listsItems"/>
                <div class="mb-24">
                    <Tags 
                        :tagsItem="tagsItem" 
                        label="Что уменьшаем?"
                    />
                </div>
            </div>
        </pPopup>
    </div>
</template>

<script>
import TextButton from '@/components/textButton'
import BigButton from '@/components/bigButton'
import pInput from '@/components/pInput'
import pPopup from '@/components/pPopup'
import Tags from '@/components/tags'
import pList from '@/components/pList'
export default {
    name: 'App',
    components: {
        TextButton,
        BigButton,
        pInput,
        pPopup,
        Tags,
        pList
    },
    data() {
        return {
            showPopup: false,
            inputValue: '',
            result: '',
            listsItems: [],
            tagsItem: [
                {
                    name: 'Платёж'
                },
                {
                    name: 'Срок'
                }
            ],
        }
    },
    methods: {
        сalculate() {
            this.listsItems = [];
            this.result = (this.inputValue * 12) * 0.13;
            this.listsItems.push(
                {price: this.result}
            );
        }
    }
}
</script>

<style>
    @font-face { 
        font-family: "LabGrotesque";
        src: url("assets/font/LabGrotesque-Regular.woff"); 
    }
    body {
        margin: 0;
        padding: 0;
        font-family: 'LabGrotesque';
    }
    .wrapper {
        background: linear-gradient(255.35deg, #DC3131 0.83%, rgba(255, 79, 79, 0) 108.93%), #FF5E56;
        box-shadow: 0px -0.11px 16.9495px rgba(183, 187, 225, 0.33);
        border-radius: 0px;
        height: 100vh;

        display: flex;
        justify-content: center;
        align-items: center;
    }
    .wrapper.scroll {
        overflow: hidden;
    }
    .popup-title {
        font-weight: 500;
        font-size: 28px;
        line-height: 40px;
        color: #000;
        margin: 0;
    }
    .popup-discription {
        font-weight: normal;
        font-size: 14px;
        line-height: 24px;
        color: #808080;
        margin: 16px 0 24px;
    }
    .mb-24 {
        margin-bottom: 24px;
    }
    .mt-8 {
        margin-top: 8px;
    }
    @media only screen and (max-width: 320px) {
        .popup-title {
            font-size: 18px;
            line-height: 24px;
        }
        .popup-discription {
            font-size: 12px;
            line-height: 16px;
        }
    }
</style>
