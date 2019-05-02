<template>
    <section class="categories">
        <div class="container">               
            <carousel :nav="false" :dots="true" :margin="30" :responsive="{0:{items:1,nav:false},600:{items:3,nav:false}}">
                <div class="categories__item">
                    <g-image class="categories__item__image" src="~/assets/images/category-img-1.jpg" width="390" height="280" fit="contain" />
                    <div class="categories__item__content">
                        <h2 class="heading h3">Ståltagplader</h2>
                        <p class="opc-7 mt-0 mb-2">Klassiske ståltagplader i forskellige varianter</p>
                        <!-- <Btn btnType="primary" text="Køb nu" /> -->
                        <g-link class="btn btn--primary" to="/">Køb nu</g-link>
                        <g-link class="btn btn--secondary" to="/">læs mere</g-link>
                    </div>
                </div>
                <div class="categories__item">
                    <g-image class="categories__item__image" src="~/assets/images/category-img-2.jpg" width="390" height="280" fit="contain" />
                    <div class="categories__item__content">
                        <h2 class="heading h3">Inddækninger</h2>
                        <p class="opc-7 mt-0 mb-2">Standard- og specialinddækninger til tag…</p>
                        <g-link class="btn btn--primary" to="/">Køb nu</g-link>
                        <g-link class="btn btn--secondary" to="/">læs mere</g-link>
                    </div>
                </div>
                <div class="categories__item">
                    <g-image class="categories__item__image" src="~/assets/images/category-img-3.jpg" width="390" height="280" fit="contain" />
                    <div class="categories__item__content">
                        <h2 class="heading h3">Stålfacade</h2>
                        <p class="opc-7 mt-0 mb-2">Beklæd og beskyt facaden med stærkt stål…</p>
                        <g-link class="btn btn--primary" to="/">Køb nu</g-link>
                        <g-link class="btn btn--secondary" to="/">læs mere</g-link>
                    </div>
                </div>
                <div class="categories__item">
                    <g-image class="categories__item__image" src="~/assets/images/category-img-1.jpg" width="390" height="280" fit="contain" />
                    <div class="categories__item__content">
                        <h2 class="heading h3">Ståltagplader</h2>
                        <p class="opc-7 mt-0 mb-2">Klassiske ståltagplader i forskellige varianter</p>
                        <g-link class="btn btn--primary" to="/">Køb nu</g-link>
                        <g-link class="btn btn--secondary" to="/">læs mere</g-link>
                    </div>
                </div>
            </carousel>
        </div>
    </section>
</template>

<script>
import carousel from 'vue-owl-carousel'
import Btn from '~/elements/Btn.vue'

export default {
    components: { 
        carousel,
        Btn
    },
}

</script>

<style lang="scss">

.categories{

    > div{
        position: relative;
    }
   
    .owl-carousel{
        width: calc(100% - 14rem);
         

        .owl-stage-outer{
            min-width: 100%;
            
        }
        
        .owl-stage{
            display: grid;
            grid-auto-flow: column;
        }

        div.owl-dots{
            height: 15vw;
            position: absolute;
            top: 0;
            right: -17rem;
            width: 14rem;

            .owl-dot{
                position: relative;
                width: 50%;
                height: 100%;
                background-color: rgba($black, .1);
                span{
                    display: none;
                }
                &:after{
                    content: "";
                    background-image: url('../assets/images/arrow-light.svg');
                    background-repeat: no-repeat;
                    background-size: 10px;
                    width: 20px;
                    height: 20px;
                    position: absolute;
                    top: 50%;
                    left: 50%;
                    transform: translate(-50%)
                }
                &:last-child:after{
                    transform: rotate(180deg) translate(50%)
                }
            }

            .active{
                background-color: $dark-gray-light;
            }
        }





        div.owl-nav.disabled + .owl-dots{
            margin: 0;
        }

        
    }

}


</style>


<style lang="scss" scoped>

.container{
    margin-top: -10rem;
}

.categories{
  background-color: $dark-gray-dark;
  color: $white;
  padding-bottom: 9rem;

  &__item{

      img{
          height: 15vw;
          object-fit: cover;
      }

      &__content{

          .heading{

          }

          p{
              font-size: 1.8rem;
          }

          .btn{
            margin-right: $gutter / 2;

            &--secondary{
                opacity: .5;
                &:hover{
                    opacity: 1;
                }
            }
          }

          
      }
      
  }

}

</style>

