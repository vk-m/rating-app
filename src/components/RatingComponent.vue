<template>
    <div class="rating-component">
        <div class="reviews">
            <div class="google">
                <svg width="40" height="40" viewBox="0 0 40 40" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <path fill-rule="evenodd" clip-rule="evenodd" d="M39.2022 20.4562C39.2034 19.0844 39.082 17.7153 38.8393 16.3652H20V24.1011H30.764C30.5419 25.3251 30.0736 26.4912 29.3876 27.5289C28.7016 28.5666 27.8121 29.4543 26.773 30.1382V35.1573H33.2371C37.0191 31.6742 39.2011 26.5472 39.2011 20.4562H39.2022Z" fill="#3E82F1" />
                    <path fill-rule="evenodd" clip-rule="evenodd" d="M20 40C25.4 40 29.9281 38.209 33.2371 35.155L26.773 30.1359C24.982 31.3359 22.691 32.0461 20 32.0461C14.791 32.0461 10.3809 28.5281 8.80898 23.8H2.12695V28.9888C3.79299 32.3002 6.34657 35.0835 9.50263 37.0279C12.6587 38.9722 16.293 40.0012 20 40Z" fill="#32A753" />
                    <path fill-rule="evenodd" clip-rule="evenodd" d="M8.81007 23.8011C7.9726 21.337 7.9726 18.6652 8.81007 16.2011V11.0191H2.12692C0.728309 13.8069 0 16.8827 0 20.0017C0 23.1206 0.728309 26.1965 2.12692 28.9843L8.81007 23.8011Z" fill="#F9BB00" />
                    <path d="M2.12695 11.0191L8.8101 16.2011C10.3831 11.473 14.7921 7.95506 20.0011 7.95506C22.9382 7.95506 25.5741 8.96629 27.6472 10.9461L33.3843 5.20899C29.9202 1.98202 25.3932 1.22836e-06 20 1.22836e-06C16.2921 -0.00129831 12.6568 1.02856 9.50054 2.97447C6.34426 4.92039 3.79129 7.70569 2.12695 11.0191Z" fill="#E74133" />
                </svg>
                <span class="google-text">Відгуки наших клієнтів у Google</span>
            </div>
            <div class="rating">
                <span class="rating-value">{{ rating }}</span>
                <span class="stars">
                    <span class="star" v-for="rating in ratings">
                        <span v-if="rating == 1" class="full">
                            <svg viewBox="0 0 28 28" fill="none" xmlns="http://www.w3.org/2000/svg">
                                <path d="M13.1033 0.816983C13.4701 0.0737376 14.5299 0.0737399 14.8967 0.816985L18.1757 7.46093C18.3214 7.75607 18.6029 7.96064 18.9287 8.00797L26.2607 9.07338C27.0809 9.19256 27.4084 10.2005 26.8149 10.7791L21.5094 15.9507C21.2737 16.1804 21.1662 16.5114 21.2218 16.8358L22.4743 24.1382C22.6144 24.9551 21.7569 25.5781 21.0233 25.1924L14.4653 21.7446C14.174 21.5915 13.826 21.5915 13.5347 21.7446L6.9767 25.1924C6.24307 25.5781 5.38563 24.9551 5.52574 24.1382L6.7782 16.8358C6.83384 16.5114 6.72629 16.1804 6.49061 15.9507L1.1851 10.7791C0.591586 10.2005 0.919094 9.19256 1.73931 9.07338L9.07134 8.00797C9.39705 7.96064 9.67862 7.75607 9.82428 7.46093L13.1033 0.816983Z" fill="#FCC141" />
                            </svg>
                        </span>

                        <span v-else-if="rating == 0" class="zero">
                            <svg viewBox="0 0 30 30" fill="none" xmlns="http://www.w3.org/2000/svg">
                                <path d="M15 2.25955L18.279 8.9035C18.5703 9.49378 19.1334 9.90292 19.7849 9.99758L27.1169 11.063L21.8114 16.2346C21.34 16.694 21.1249 17.356 21.2362 18.0048L22.4886 25.3072L15.9307 21.8595C15.348 21.5532 14.652 21.5532 14.0693 21.8595L7.51135 25.3072L8.76381 18.0048C8.87509 17.3561 8.65999 16.694 8.18862 16.2346L2.88312 11.063L10.2151 9.99758C10.8666 9.90292 11.4297 9.49379 11.721 8.9035L15 2.25955Z" stroke="#FCC141" stroke-width="2" />
                            </svg>
                        </span>

                        <span v-else class="half">
                            <svg viewBox="0 0 30 30" fill="none" xmlns="http://www.w3.org/2000/svg">
                                <path d="M15 2.25955L18.279 8.9035C18.5703 9.49378 19.1334 9.90292 19.7849 9.99758L27.1169 11.063L21.8114 16.2346C21.34 16.694 21.1249 17.356 21.2362 18.0048L22.4886 25.3072L15.9307 21.8595C15.348 21.5532 14.652 21.5532 14.0693 21.8595L7.51135 25.3072L8.76381 18.0048C8.87509 17.3561 8.65999 16.694 8.18862 16.2346L2.88312 11.063L10.2151 9.99758C10.8666 9.90292 11.4297 9.49379 11.721 8.9035L15 2.25955Z" stroke="#FCC141" stroke-width="2" />
                                <mask id="mask0_1_600" style="mask-type:alpha" maskUnits="userSpaceOnUse" x="1" y="1" width="28" height="26">
                                    <path d="M14.1033 1.81698C14.4701 1.07374 15.5299 1.07374 15.8967 1.81699L19.1757 8.46093C19.3214 8.75607 19.6029 8.96064 19.9287 9.00797L27.2607 10.0734C28.0809 10.1926 28.4084 11.2005 27.8149 11.7791L22.5094 16.9507C22.2737 17.1804 22.1662 17.5114 22.2218 17.8358L23.4743 25.1382C23.6144 25.9551 22.7569 26.5781 22.0233 26.1924L15.4653 22.7446C15.174 22.5915 14.826 22.5915 14.5347 22.7446L7.9767 26.1924C7.24307 26.5781 6.38563 25.9551 6.52574 25.1382L7.7782 17.8358C7.83384 17.5114 7.72629 17.1804 7.49061 16.9507L2.1851 11.7791C1.59159 11.2005 1.91909 10.1926 2.73931 10.0734L10.0713 9.00797C10.3971 8.96064 10.6786 8.75607 10.8243 8.46093L14.1033 1.81698Z" fill="#FCC141" />
                                </mask>
                                <g mask="url(#mask0_1_600)">
                                    <rect width="15" height="30" fill="#FCC141" />
                                </g>
                            </svg>
                        </span>
                    </span>
                </span>
                <span class="reviews-count"> ({{ reviewsCount }} відгуки)</span>
            </div>
        </div>
        <div class="buttons">
            <button @click="redirectToGoogle" class="btn btn-secondary">Переглянути</button>
            <button @click="openModal" class="btn btn-primary">Написати</button>

            <ModalForm :isOpen="isModalOpen" @close="closeModal" @submit="handleSubmit" />
            <Notification v-if="notification.message" :message="notification.message" />
        </div>
    </div>
</template>

<script setup lang="ts">
import { ref, onMounted } from 'vue';

import ModalForm from './ModalForm.vue';
import Notification from './Notification.vue';

const rating = ref(0);
const ratings = ref([0]);
const reviewsCount = ref(0);

const isModalOpen = ref(false);

const notification = ref({
    message: ''
});

const openModal = () => {
    isModalOpen.value = true;
};

const closeModal = () => {
    isModalOpen.value = false;
};

const handleSubmit = (message: string) => {
    notification.value = {
        message: `Повідомлення надіслано - ${message}`
    };
};


const fetchData = async () => {
    const response = await fetch('https://6798a8d7be2191d708b06ac6.mockapi.io/reviews');
    const data = await response.json();

    if (data != null && data.length > 0) {
        rating.value = data[0].rating;
        ratings.value = splitNumber(data[0].rating);
        reviewsCount.value = data[0].reviewsCount;
    }
};

onMounted(() => {
    fetchData();
});

const redirectToGoogle = () => {
    window.location.href = 'https://www.google.com';
};

function splitNumber(num: number) {
    const result = [0, 0, 0, 0, 0];
    let remaining = num;

    for (let i = 0; i < result.length; i++) {
        if (remaining >= 1) {
            result[i] = 1;
            remaining -= 1;
        } else {
            result[i] = remaining;
            break;
        }
    }

    return result;
}
</script>

<style scoped lang="scss">
.rating-component {
    padding: 20px;
    border-radius: 8px;
    text-align: center;
    display: flex;
    justify-content: space-between;
    align-items: center;
    background: rgba(255, 255, 255, 1);
    box-shadow: 0px 4px 15px 0px rgba(0, 0, 0, 0.05);

    .reviews {
        display: flex;
        align-items: center;
        gap: 60px;

        .google,
        .rating {
            display: flex;
            align-content: center;
            align-items: center;
            gap: 20px;

            .rating-value {
                font-family: Greenwich;
                font-size: 36px;
                font-weight: 500;
                line-height: 44px;
                text-align: left;
                text-underline-position: from-font;
                text-decoration-skip-ink: none;
                color: rgba(57, 65, 85, 1);
            }

            .stars {
                padding-top: 8px;

                svg {
                    width: 30px;
                    height: 30px;
                }
            }

            .reviews-count {
                font-family: Formular;
                font-size: 14px;
                font-weight: 300;
                line-height: 22px;
                text-align: left;
                text-underline-position: from-font;
                text-decoration-skip-ink: none;
                color: rgba(121, 133, 149, 1);
            }
        }
    }

    @media screen and (min-width: 1366px) {
        max-width: 1418px;
    }

    @media screen and (max-width: 1199px) {
        .reviews {
            align-items: flex-start;
            flex-direction: column;
            gap: 0px;

            .rating {
                .rating-value {
                    font-size: 24px;
                    line-height: 32px;
                }

                .stars {
                    gap: 6px;
                    display: flex;

                    svg {
                        width: 30px;
                        height: 30px;
                    }
                }
            }
        }
    }

    @media screen and (max-width: 768px) {
        flex-direction: column;
        gap: 20px;

        .google-text {
            width: 80%;
            text-align: left;
        }

        .buttons {
            display: flex;
            flex-direction: column;
            gap: 10px;
            width: 100%;
            max-width: 360px;
        }
    }

    @media screen and (max-width: 360px) {
        .reviews {
            .google {
                .google-text {
                    font-size: 18px;
                    line-height: 26px;
                    text-align: left;
                }
            }

            .rating {
                gap: 6px;
                flex-flow: wrap;
            }

            .stars {
                margin-left: 14px;
            }
        }
    }
}
</style>