<template>
  <nav>
    <div class="drawer lg:drawer-open">
      <input id="my-drawer-2" type="checkbox" class="drawer-toggle" />
      <div class="drawer-content flex flex-col items-center justify-center">
        <!-- Page content here -->
        <label for="my-drawer-2" class="lg:hidden btn btn-square btn-ghost">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            class="inline-block w-6 h-6 stroke-current"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M4 6h16M4 12h16M4 18h16"
            ></path>
          </svg>
        </label>
      </div>

      <div class="drawer-side">
        <label for="my-drawer-2" class="drawer-overlay"></label>
        <div class="flex flex-col flex-nowrap p-4 w-70 h-full bg-base-200 text-base-content">
          <div class="flex flex-row gap-5 mx-auto">
            <c-input v-model="size.w" label="Width" class="w-20" />
            <c-input v-model="size.h" label="Height" class="w-20" />
          </div>
          <p class="menu-title">DMC Colors</p>
          <ul class="grow overflow-auto">
            <c-color-item v-for="c in DMCCOLORS" :key="c.RGB_COLOR" :color="c" />
          </ul>
        </div>
      </div>
    </div>
  </nav>
</template>

<script setup lang="ts">
import CInput from '@/components/CInput.vue';
import CColorItem from '@/components/CColorItem.vue';

const size = defineModel<{ w: number; h: number }>({ default: { w: 10, h: 15 } });

const DMCCOLORS = [
  {
    DMC_COLOR: 'Ecru',
    COLOR_NAME: ' Ecru/off-white',
    RGB_COLOR: ' #fff7e7'
  },
  {
    DMC_COLOR: '315',
    COLOR_NAME: ' Antique Mauve - MED DK',
    RGB_COLOR: ' #7d4246'
  },
  {
    DMC_COLOR: 'Blanc',
    COLOR_NAME: ' White',
    RGB_COLOR: ' #eeeeee'
  },
  {
    DMC_COLOR: '316',
    COLOR_NAME: ' Antique Mauve - MED',
    RGB_COLOR: ' #bc757f'
  },
  {
    DMC_COLOR: 'B5200',
    COLOR_NAME: ' Snow White',
    RGB_COLOR: ' #fcfcff'
  },
  {
    DMC_COLOR: '317',
    COLOR_NAME: ' Pewter Gray',
    RGB_COLOR: ' #6d6469'
  },
  {
    DMC_COLOR: 'White',
    COLOR_NAME: ' White',
    RGB_COLOR: ' #ffffff'
  },
  {
    DMC_COLOR: '318',
    COLOR_NAME: ' Steel Gray - LT',
    RGB_COLOR: ' #999b9d'
  },
  {
    DMC_COLOR: '150',
    COLOR_NAME: ' Red - BRIGHT',
    RGB_COLOR: ' #cf0053'
  },
  {
    DMC_COLOR: '319',
    COLOR_NAME: ' Pistachio Green - VY DK',
    RGB_COLOR: ' #3a553b'
  },
  {
    DMC_COLOR: '151',
    COLOR_NAME: ' Pink',
    RGB_COLOR: ' #ffcbd7'
  },
  {
    DMC_COLOR: '320',
    COLOR_NAME: ' Pistachio Green - MED',
    RGB_COLOR: ' #608c59'
  },
  {
    DMC_COLOR: '152',
    COLOR_NAME: ' Tawny - DK',
    RGB_COLOR: ' #e1a1a1'
  },
  {
    DMC_COLOR: '321',
    COLOR_NAME: ' Red',
    RGB_COLOR: ' #bd1136'
  },
  {
    DMC_COLOR: '153',
    COLOR_NAME: ' Lilac',
    RGB_COLOR: ' #eac5eb'
  },
  {
    DMC_COLOR: '322',
    COLOR_NAME: ' Baby Blue',
    RGB_COLOR: ' #3a609d'
  },
  {
    DMC_COLOR: '154',
    COLOR_NAME: ' Red - VY DK',
    RGB_COLOR: ' #4b233a'
  },
  {
    DMC_COLOR: '326',
    COLOR_NAME: ' Rose - VY DK',
    RGB_COLOR: ' #ac1c37'
  },
  {
    DMC_COLOR: '155',
    COLOR_NAME: ' Forget-me-not Blue',
    RGB_COLOR: ' #9774b6'
  },
  {
    DMC_COLOR: '327',
    COLOR_NAME: ' Violet',
    RGB_COLOR: ' #5e0f77'
  },
  {
    DMC_COLOR: '156',
    COLOR_NAME: ' Blue - MED',
    RGB_COLOR: ' #8577b4'
  },
  {
    DMC_COLOR: '333',
    COLOR_NAME: ' Blue Violet - VY DK',
    RGB_COLOR: ' #6e2e9b'
  },
  {
    DMC_COLOR: '157',
    COLOR_NAME: ' Blue - LT',
    RGB_COLOR: ' #b5b8ea'
  },
  {
    DMC_COLOR: '334',
    COLOR_NAME: ' Baby Blue - MED',
    RGB_COLOR: ' #6085b8'
  },
  {
    DMC_COLOR: '158',
    COLOR_NAME: ' Blue - DK',
    RGB_COLOR: ' #393068'
  },
  {
    DMC_COLOR: '335',
    COLOR_NAME: ' Rose',
    RGB_COLOR: ' #d63d57'
  },
  {
    DMC_COLOR: '159',
    COLOR_NAME: ' Petrol Blue - LT',
    RGB_COLOR: ' #bcb5de'
  },
  {
    DMC_COLOR: '336',
    COLOR_NAME: ' Blue',
    RGB_COLOR: ' #0c275e'
  },
  {
    DMC_COLOR: '160',
    COLOR_NAME: ' Petrol Blue - MED',
    RGB_COLOR: ' #8178a9'
  },
  {
    DMC_COLOR: '340',
    COLOR_NAME: ' Blue Violet - MED',
    RGB_COLOR: ' #996dc3'
  },
  {
    DMC_COLOR: '161',
    COLOR_NAME: ' Petrol Blue - DK',
    RGB_COLOR: ' #60568b'
  },
  {
    DMC_COLOR: '341',
    COLOR_NAME: ' Blue Violet - LT',
    RGB_COLOR: ' #a39ad7'
  },
  {
    DMC_COLOR: '162',
    COLOR_NAME: ' Baby Blue - LT',
    RGB_COLOR: ' #cae7f0'
  },
  {
    DMC_COLOR: '347',
    COLOR_NAME: ' Salmon - VY DK',
    RGB_COLOR: ' #ab1b33'
  },
  {
    DMC_COLOR: '163',
    COLOR_NAME: ' Green',
    RGB_COLOR: ' #557a60'
  },
  {
    DMC_COLOR: '349',
    COLOR_NAME: ' Coral - DK',
    RGB_COLOR: ' #c62c38'
  },
  {
    DMC_COLOR: '164',
    COLOR_NAME: ' Green - LT',
    RGB_COLOR: ' #bae4b6'
  },
  {
    DMC_COLOR: '350',
    COLOR_NAME: ' Coral - MED',
    RGB_COLOR: ' #de3f40'
  },
  {
    DMC_COLOR: '165',
    COLOR_NAME: ' Green - BRIGHT',
    RGB_COLOR: ' #e1f477'
  },
  {
    DMC_COLOR: '351',
    COLOR_NAME: ' Coral',
    RGB_COLOR: ' #ed625b'
  },
  {
    DMC_COLOR: '166',
    COLOR_NAME: ' Lime Green',
    RGB_COLOR: ' #adc238'
  },
  {
    DMC_COLOR: '352',
    COLOR_NAME: ' Coral - LT',
    RGB_COLOR: ' #f78372'
  },
  {
    DMC_COLOR: '167',
    COLOR_NAME: ' Khaki Brown',
    RGB_COLOR: ' #855d31'
  },
  {
    DMC_COLOR: '353',
    COLOR_NAME: ' Peach',
    RGB_COLOR: ' #fdb4a1'
  },
  {
    DMC_COLOR: '168',
    COLOR_NAME: ' Silver Gray',
    RGB_COLOR: ' #b1aeb7'
  },
  {
    DMC_COLOR: '355',
    COLOR_NAME: ' Terra Cotta - DK',
    RGB_COLOR: ' #97382b'
  },
  {
    DMC_COLOR: '169',
    COLOR_NAME: ' Pewter Gray',
    RGB_COLOR: ' #827d7d'
  },
  {
    DMC_COLOR: '356',
    COLOR_NAME: ' Terra Cotta - MED',
    RGB_COLOR: ' #be5c4b'
  },
  {
    DMC_COLOR: '208',
    COLOR_NAME: ' Lavender - VY DK',
    RGB_COLOR: ' #9442a7'
  },
  {
    DMC_COLOR: '367',
    COLOR_NAME: ' Pistachio Green - DK',
    RGB_COLOR: ' #446b45'
  },
  {
    DMC_COLOR: '209',
    COLOR_NAME: ' Lavender - DK',
    RGB_COLOR: ' #ba72c6'
  },
  {
    DMC_COLOR: '368',
    COLOR_NAME: ' Pistachio Green - LT',
    RGB_COLOR: ' #7fc66d'
  },
  {
    DMC_COLOR: '210',
    COLOR_NAME: ' Lavender - MED',
    RGB_COLOR: ' #d49fe1'
  },
  {
    DMC_COLOR: '369',
    COLOR_NAME: ' Pistachio Green - VY LT',
    RGB_COLOR: ' #cdefa6'
  },
  {
    DMC_COLOR: '211',
    COLOR_NAME: ' Lavender - LT',
    RGB_COLOR: ' #e5bded'
  },
  {
    DMC_COLOR: '370',
    COLOR_NAME: ' Mustard - MED',
    RGB_COLOR: ' #917245'
  },
  {
    DMC_COLOR: '221',
    COLOR_NAME: ' Shell Pink - VY DK',
    RGB_COLOR: ' #792631'
  },
  {
    DMC_COLOR: '371',
    COLOR_NAME: ' Mustard',
    RGB_COLOR: ' #9f8352'
  },
  {
    DMC_COLOR: '223',
    COLOR_NAME: ' Shell Pink - LT',
    RGB_COLOR: ' #bb6864'
  },
  {
    DMC_COLOR: '372',
    COLOR_NAME: ' Mustard - LT',
    RGB_COLOR: ' #ad9564'
  },
  {
    DMC_COLOR: '224',
    COLOR_NAME: ' Shell Pink - VY LT',
    RGB_COLOR: ' #e2a598'
  },
  {
    DMC_COLOR: '400',
    COLOR_NAME: ' Mahogany - DK',
    RGB_COLOR: ' #813718'
  },
  {
    DMC_COLOR: '225',
    COLOR_NAME: ' Shell Pink - ULT VY LT',
    RGB_COLOR: ' #f8d9cd'
  },
  {
    DMC_COLOR: '402',
    COLOR_NAME: ' Mahogany - VY LT',
    RGB_COLOR: ' #ef9e74'
  },
  {
    DMC_COLOR: '300',
    COLOR_NAME: ' Mahogany - VY DK',
    RGB_COLOR: ' #6c3116'
  },
  {
    DMC_COLOR: '407',
    COLOR_NAME: ' Desert Sand - DK',
    RGB_COLOR: ' #b77159'
  },
  {
    DMC_COLOR: '301',
    COLOR_NAME: ' Mahogany - MED',
    RGB_COLOR: ' #aa5237'
  },
  {
    DMC_COLOR: '413',
    COLOR_NAME: ' Pewter Gray - DK',
    RGB_COLOR: ' #4a4749'
  },
  {
    DMC_COLOR: '304',
    COLOR_NAME: ' Red - MED',
    RGB_COLOR: ' #a10c39'
  },
  {
    DMC_COLOR: '414',
    COLOR_NAME: ' Steel Gray - DK',
    RGB_COLOR: ' #766e72'
  },
  {
    DMC_COLOR: '307',
    COLOR_NAME: ' Lemon',
    RGB_COLOR: ' #fde949'
  },
  {
    DMC_COLOR: '415',
    COLOR_NAME: ' Pearl Gray',
    RGB_COLOR: ' #b8b9bd'
  },
  {
    DMC_COLOR: '309',
    COLOR_NAME: ' Rose - DK',
    RGB_COLOR: ' #ba2044'
  },
  {
    DMC_COLOR: '420',
    COLOR_NAME: ' Hazelnut Brown - DK',
    RGB_COLOR: ' #855a30'
  },
  {
    DMC_COLOR: '310',
    COLOR_NAME: ' Black',
    RGB_COLOR: ' #000000'
  },
  {
    DMC_COLOR: '422',
    COLOR_NAME: ' Hazelnut Brown - LT',
    RGB_COLOR: ' #c99a67'
  },
  {
    DMC_COLOR: '311',
    COLOR_NAME: ' Blue - MED',
    RGB_COLOR: ' #002a64'
  },
  {
    DMC_COLOR: '433',
    COLOR_NAME: ' Brown - MED',
    RGB_COLOR: ' #73421e'
  },
  {
    DMC_COLOR: '312',
    COLOR_NAME: ' Baby Blue - VY DK',
    RGB_COLOR: ' #1f3279'
  },
  {
    DMC_COLOR: '434',
    COLOR_NAME: ' Brown - LT',
    RGB_COLOR: ' #8f5332'
  },
  {
    DMC_COLOR: '435',
    COLOR_NAME: ' Brown - VY LT',
    RGB_COLOR: ' #a96538'
  },
  {
    DMC_COLOR: '600',
    COLOR_NAME: ' Cranberry - VY DK',
    RGB_COLOR: ' #bf1c48'
  },
  {
    DMC_COLOR: '436',
    COLOR_NAME: ' Tan',
    RGB_COLOR: ' #c78559'
  },
  {
    DMC_COLOR: '601',
    COLOR_NAME: ' Cranberry - DK',
    RGB_COLOR: ' #c62a53'
  },
  {
    DMC_COLOR: '437',
    COLOR_NAME: ' Tan - LT',
    RGB_COLOR: ' #daa26f'
  },
  {
    DMC_COLOR: '602',
    COLOR_NAME: ' Cranberry - MED',
    RGB_COLOR: ' #d63f68'
  },
  {
    DMC_COLOR: '444',
    COLOR_NAME: ' Lemon - DK',
    RGB_COLOR: ' #f5bc13'
  },
  {
    DMC_COLOR: '603',
    COLOR_NAME: ' Cranberry',
    RGB_COLOR: ' #ed5d84'
  },
  {
    DMC_COLOR: '445',
    COLOR_NAME: ' Lemon - LT',
    RGB_COLOR: ' #fcf999'
  },
  {
    DMC_COLOR: '604',
    COLOR_NAME: ' Cranberry - LT',
    RGB_COLOR: ' #f793b2'
  },
  {
    DMC_COLOR: '451',
    COLOR_NAME: ' Shell Gray - DK',
    RGB_COLOR: ' #887773'
  },
  {
    DMC_COLOR: '605',
    COLOR_NAME: ' Cranberry - VY LT',
    RGB_COLOR: ' #fbacc4'
  },
  {
    DMC_COLOR: '452',
    COLOR_NAME: ' Shell Gray - MED',
    RGB_COLOR: ' #ad9994'
  },
  {
    DMC_COLOR: '606',
    COLOR_NAME: ' Orange-red - BRIGHT',
    RGB_COLOR: ' #f70f00'
  },
  {
    DMC_COLOR: '453',
    COLOR_NAME: ' Shell Gray - LT',
    RGB_COLOR: ' #ccb8aa'
  },
  {
    DMC_COLOR: '608',
    COLOR_NAME: ' Orange - BRIGHT',
    RGB_COLOR: ' #fd480c'
  },
  {
    DMC_COLOR: '469',
    COLOR_NAME: ' Avocado Green',
    RGB_COLOR: ' #5b6533'
  },
  {
    DMC_COLOR: '610',
    COLOR_NAME: ' Drab Brown - DK',
    RGB_COLOR: ' #6b5039'
  },
  {
    DMC_COLOR: '470',
    COLOR_NAME: ' Avocado Green - LT',
    RGB_COLOR: ' #72813e'
  },
  {
    DMC_COLOR: '611',
    COLOR_NAME: ' Drab Brown',
    RGB_COLOR: ' #7c5f46'
  },
  {
    DMC_COLOR: '471',
    COLOR_NAME: ' Avocado Green - VY LT',
    RGB_COLOR: ' #9eb357'
  },
  {
    DMC_COLOR: '612',
    COLOR_NAME: ' Drab Brown - LT',
    RGB_COLOR: ' #a6885e'
  },
  {
    DMC_COLOR: '472',
    COLOR_NAME: ' Avocado Green - ULT LT',
    RGB_COLOR: ' #d1de75'
  },
  {
    DMC_COLOR: '613',
    COLOR_NAME: ' Drab Brown - VY LT',
    RGB_COLOR: ' #b99f72'
  },
  {
    DMC_COLOR: '498',
    COLOR_NAME: ' Red - DK',
    RGB_COLOR: ' #970b2c'
  },
  {
    DMC_COLOR: '632',
    COLOR_NAME: ' Desert Sand - ULT VY DK',
    RGB_COLOR: ' #7f4232'
  },
  {
    DMC_COLOR: '500',
    COLOR_NAME: ' Blue Green - VY DK',
    RGB_COLOR: ' #1d362a'
  },
  {
    DMC_COLOR: '640',
    COLOR_NAME: ' Beige Gray - VY DK',
    RGB_COLOR: ' #817868'
  },
  {
    DMC_COLOR: '501',
    COLOR_NAME: ' Blue Green - DK',
    RGB_COLOR: ' #2f5446'
  },
  {
    DMC_COLOR: '642',
    COLOR_NAME: ' Beige Gray - DK',
    RGB_COLOR: ' #958d79'
  },
  {
    DMC_COLOR: '502',
    COLOR_NAME: ' Blue Green',
    RGB_COLOR: ' #57826e'
  },
  {
    DMC_COLOR: '644',
    COLOR_NAME: ' Beige Gray - MED',
    RGB_COLOR: ' #c4bea6'
  },
  {
    DMC_COLOR: '503',
    COLOR_NAME: ' Blue Green - MED',
    RGB_COLOR: ' #89b89f'
  },
  {
    DMC_COLOR: '645',
    COLOR_NAME: ' Beaver Gray - VY DK',
    RGB_COLOR: ' #5d5d54'
  },
  {
    DMC_COLOR: '504',
    COLOR_NAME: ' Blue Green - VY LT',
    RGB_COLOR: ' #acdac1'
  },
  {
    DMC_COLOR: '646',
    COLOR_NAME: ' Beaver Gray - DK',
    RGB_COLOR: ' #6b6860'
  },
  {
    DMC_COLOR: '505',
    COLOR_NAME: ' Grass Green - DK',
    RGB_COLOR: ' #ceddc1'
  },
  {
    DMC_COLOR: '647',
    COLOR_NAME: ' Beaver Gray - MED',
    RGB_COLOR: ' #908e85'
  },
  {
    DMC_COLOR: '517',
    COLOR_NAME: ' Wedgewood - DK',
    RGB_COLOR: ' #216285'
  },
  {
    DMC_COLOR: '648',
    COLOR_NAME: ' Beaver Gray - LT',
    RGB_COLOR: ' #a7a69f'
  },
  {
    DMC_COLOR: '518',
    COLOR_NAME: ' Wedgewood - LT',
    RGB_COLOR: ' #50819c'
  },
  {
    DMC_COLOR: '666',
    COLOR_NAME: ' Red - BRIGHT',
    RGB_COLOR: ' #ce1b33'
  },
  {
    DMC_COLOR: '519',
    COLOR_NAME: ' Sky Blue',
    RGB_COLOR: ' #94b7cb'
  },
  {
    DMC_COLOR: '676',
    COLOR_NAME: ' Old Gold - LT',
    RGB_COLOR: ' #ecbf7d'
  },
  {
    DMC_COLOR: '520',
    COLOR_NAME: ' Fern Green - DK',
    RGB_COLOR: ' #384526'
  },
  {
    DMC_COLOR: '677',
    COLOR_NAME: ' Old Gold - VY LT',
    RGB_COLOR: ' #f2dc9f'
  },
  {
    DMC_COLOR: '522',
    COLOR_NAME: ' Fern Green',
    RGB_COLOR: ' #808b6e'
  },
  {
    DMC_COLOR: '680',
    COLOR_NAME: ' Old Gold - DK',
    RGB_COLOR: ' #b07b46'
  },
  {
    DMC_COLOR: '523',
    COLOR_NAME: ' Fern Green - LT',
    RGB_COLOR: ' #959f7a'
  },
  {
    DMC_COLOR: '699',
    COLOR_NAME: ' Green',
    RGB_COLOR: ' #075b26'
  },
  {
    DMC_COLOR: '524',
    COLOR_NAME: ' Fern Green - VY LT',
    RGB_COLOR: ' #aea78e'
  },
  {
    DMC_COLOR: '700',
    COLOR_NAME: ' Green - BRIGHT',
    RGB_COLOR: ' #076c34'
  },
  {
    DMC_COLOR: '535',
    COLOR_NAME: ' Ash Gray - VY LT',
    RGB_COLOR: ' #4b4b49'
  },
  {
    DMC_COLOR: '701',
    COLOR_NAME: ' Green - LT',
    RGB_COLOR: ' #217c36'
  },
  {
    DMC_COLOR: '543',
    COLOR_NAME: ' Beige Brown - ULT VY LT',
    RGB_COLOR: ' #ead0b5'
  },
  {
    DMC_COLOR: '702',
    COLOR_NAME: ' Kelly Green',
    RGB_COLOR: ' #379130'
  },
  {
    DMC_COLOR: '550',
    COLOR_NAME: ' Violet - VY DK',
    RGB_COLOR: ' #580e5c'
  },
  {
    DMC_COLOR: '703',
    COLOR_NAME: ' Chartreuse',
    RGB_COLOR: ' #63b330'
  },
  {
    DMC_COLOR: '552',
    COLOR_NAME: ' Violet - MED',
    RGB_COLOR: ' #902f99'
  },
  {
    DMC_COLOR: '704',
    COLOR_NAME: ' Chartreuse - BRIGHT',
    RGB_COLOR: ' #88c53a'
  },
  {
    DMC_COLOR: '553',
    COLOR_NAME: ' Violet',
    RGB_COLOR: ' #a449ac'
  },
  {
    DMC_COLOR: '712',
    COLOR_NAME: ' Cream',
    RGB_COLOR: ' #f6efda'
  },
  {
    DMC_COLOR: '554',
    COLOR_NAME: ' Violet - LT',
    RGB_COLOR: ' #dc9cde'
  },
  {
    DMC_COLOR: '718',
    COLOR_NAME: ' Plum',
    RGB_COLOR: ' #cb2089'
  },
  {
    DMC_COLOR: '561',
    COLOR_NAME: ' Jade - VY DK',
    RGB_COLOR: ' #285e48'
  },
  {
    DMC_COLOR: '720',
    COLOR_NAME: ' Orange Spice - DK',
    RGB_COLOR: ' #c83a24'
  },
  {
    DMC_COLOR: '562',
    COLOR_NAME: ' Jade - MED',
    RGB_COLOR: ' #3b8c5a'
  },
  {
    DMC_COLOR: '721',
    COLOR_NAME: ' Orange Spice - MED',
    RGB_COLOR: ' #f46440'
  },
  {
    DMC_COLOR: '563',
    COLOR_NAME: ' Jade - LT',
    RGB_COLOR: ' #6ed39a'
  },
  {
    DMC_COLOR: '722',
    COLOR_NAME: ' Orange Spice - LT',
    RGB_COLOR: ' #f98756'
  },
  {
    DMC_COLOR: '564',
    COLOR_NAME: ' Jade - VY LT',
    RGB_COLOR: ' #95e4af'
  },
  {
    DMC_COLOR: '725',
    COLOR_NAME: ' Topaz',
    RGB_COLOR: ' #f9c15b'
  },
  {
    DMC_COLOR: '580',
    COLOR_NAME: ' Moss Green - DK',
    RGB_COLOR: ' #355f0b'
  },
  {
    DMC_COLOR: '726',
    COLOR_NAME: ' Topaz - LT',
    RGB_COLOR: ' #fddb63'
  },
  {
    DMC_COLOR: '581',
    COLOR_NAME: ' Moss Green',
    RGB_COLOR: ' #838a29'
  },
  {
    DMC_COLOR: '727',
    COLOR_NAME: ' Topaz - VY LT',
    RGB_COLOR: ' #fde98b'
  },
  {
    DMC_COLOR: '597',
    COLOR_NAME: ' Turquoise',
    RGB_COLOR: ' #52adab'
  },
  {
    DMC_COLOR: '728',
    COLOR_NAME: ' Golden Yellow',
    RGB_COLOR: ' #f2ae3f'
  },
  {
    DMC_COLOR: '598',
    COLOR_NAME: ' Turquoise - LT',
    RGB_COLOR: ' #97d8d3'
  },
  {
    DMC_COLOR: '729',
    COLOR_NAME: ' Old Gold - MED',
    RGB_COLOR: ' #ce9657'
  },
  {
    DMC_COLOR: '730',
    COLOR_NAME: ' Olive Green - VY DK',
    RGB_COLOR: ' #63520b'
  },
  {
    DMC_COLOR: '803',
    COLOR_NAME: ' Blue - DEEP',
    RGB_COLOR: ' #202754'
  },
  {
    DMC_COLOR: '731',
    COLOR_NAME: ' Olive Green - DK',
    RGB_COLOR: ' #6b580b'
  },
  {
    DMC_COLOR: '806',
    COLOR_NAME: ' Peacock Blue - DK',
    RGB_COLOR: ' #1d6c87'
  },
  {
    DMC_COLOR: '732',
    COLOR_NAME: ' Olive Green',
    RGB_COLOR: ' #725c0c'
  },
  {
    DMC_COLOR: '807',
    COLOR_NAME: ' Peacock Blue',
    RGB_COLOR: ' #558b9e'
  },
  {
    DMC_COLOR: '733',
    COLOR_NAME: ' Olive Green - MED',
    RGB_COLOR: ' #a78a44'
  },
  {
    DMC_COLOR: '809',
    COLOR_NAME: ' Delft Blue',
    RGB_COLOR: ' #919fd5'
  },
  {
    DMC_COLOR: '734',
    COLOR_NAME: ' Olive Green - LT',
    RGB_COLOR: ' #bb9c54'
  },
  {
    DMC_COLOR: '813',
    COLOR_NAME: ' Blue - LT',
    RGB_COLOR: ' #7fa0c6'
  },
  {
    DMC_COLOR: '738',
    COLOR_NAME: ' Tan - VY LT',
    RGB_COLOR: ' #e2b783'
  },
  {
    DMC_COLOR: '814',
    COLOR_NAME: ' Garnet - DK',
    RGB_COLOR: ' #711033'
  },
  {
    DMC_COLOR: '739',
    COLOR_NAME: ' Tan - ULT VY LT',
    RGB_COLOR: ' #f2deb9'
  },
  {
    DMC_COLOR: '815',
    COLOR_NAME: ' Garnet - MED',
    RGB_COLOR: ' #800b34'
  },
  {
    DMC_COLOR: '740',
    COLOR_NAME: ' Tangerine',
    RGB_COLOR: ' #fd6f1a'
  },
  {
    DMC_COLOR: '816',
    COLOR_NAME: ' Garnet',
    RGB_COLOR: ' #921238'
  },
  {
    DMC_COLOR: '741',
    COLOR_NAME: ' Tangerine - MED',
    RGB_COLOR: ' #fc8b10'
  },
  {
    DMC_COLOR: '817',
    COLOR_NAME: ' Coral Red - VY DK',
    RGB_COLOR: ' #bb1630'
  },
  {
    DMC_COLOR: '742',
    COLOR_NAME: ' Tangerine - LT',
    RGB_COLOR: ' #fdae3c'
  },
  {
    DMC_COLOR: '818',
    COLOR_NAME: ' Baby Pink',
    RGB_COLOR: ' #fededd'
  },
  {
    DMC_COLOR: '743',
    COLOR_NAME: ' Yellow - MED',
    RGB_COLOR: ' #fdd769'
  },
  {
    DMC_COLOR: '819',
    COLOR_NAME: ' Baby Pink - LT',
    RGB_COLOR: ' #fcebde'
  },
  {
    DMC_COLOR: '744',
    COLOR_NAME: ' Yellow - PALE',
    RGB_COLOR: ' #fee88d'
  },
  {
    DMC_COLOR: '820',
    COLOR_NAME: ' Royal Blue - VY DK',
    RGB_COLOR: ' #151264'
  },
  {
    DMC_COLOR: '745',
    COLOR_NAME: ' Yellow - LT PALE',
    RGB_COLOR: ' #feeba5'
  },
  {
    DMC_COLOR: '822',
    COLOR_NAME: ' Beige Gray - LT',
    RGB_COLOR: ' #e8dfc7'
  },
  {
    DMC_COLOR: '746',
    COLOR_NAME: ' Off White',
    RGB_COLOR: ' #faf2d5'
  },
  {
    DMC_COLOR: '823',
    COLOR_NAME: ' Blue - DK',
    RGB_COLOR: ' #000b44'
  },
  {
    DMC_COLOR: '747',
    COLOR_NAME: ' Sky Blue - VY LT',
    RGB_COLOR: ' #cee9ea'
  },
  {
    DMC_COLOR: '824',
    COLOR_NAME: ' Blue - VY DK',
    RGB_COLOR: ' #284779'
  },
  {
    DMC_COLOR: '754',
    COLOR_NAME: ' Peach - LT',
    RGB_COLOR: ' #f7c9b0'
  },
  {
    DMC_COLOR: '825',
    COLOR_NAME: ' Blue - DK',
    RGB_COLOR: ' #34588f'
  },
  {
    DMC_COLOR: '758',
    COLOR_NAME: ' Terra Cotta - VY LT',
    RGB_COLOR: ' #e99f83'
  },
  {
    DMC_COLOR: '826',
    COLOR_NAME: ' Blue - MED',
    RGB_COLOR: ' #5075a7'
  },
  {
    DMC_COLOR: '760',
    COLOR_NAME: ' Salmon',
    RGB_COLOR: ' #ec8880'
  },
  {
    DMC_COLOR: '827',
    COLOR_NAME: ' Blue - VY LT',
    RGB_COLOR: ' #a4c1de'
  },
  {
    DMC_COLOR: '761',
    COLOR_NAME: ' Salmon - LT',
    RGB_COLOR: ' #f8b4ad'
  },
  {
    DMC_COLOR: '828',
    COLOR_NAME: ' Blue - ULT VY LT',
    RGB_COLOR: ' #c3d7e6'
  },
  {
    DMC_COLOR: '762',
    COLOR_NAME: ' Pearl Gray - VY LT',
    RGB_COLOR: ' #d1d0d2'
  },
  {
    DMC_COLOR: '829',
    COLOR_NAME: ' Golden Olive - VY DK',
    RGB_COLOR: ' #64480c'
  },
  {
    DMC_COLOR: '772',
    COLOR_NAME: ' Yellow Green - VY LT',
    RGB_COLOR: ' #d7efa7'
  },
  {
    DMC_COLOR: '830',
    COLOR_NAME: ' Golden Olive - DK',
    RGB_COLOR: ' #6e501d'
  },
  {
    DMC_COLOR: '775',
    COLOR_NAME: ' Baby Blue - VY LT',
    RGB_COLOR: ' #d4e3ef'
  },
  {
    DMC_COLOR: '831',
    COLOR_NAME: ' Golden Olive - MED',
    RGB_COLOR: ' #7c5f20'
  },
  {
    DMC_COLOR: '776',
    COLOR_NAME: ' Pink - MED',
    RGB_COLOR: ' #fca8ad'
  },
  {
    DMC_COLOR: '832',
    COLOR_NAME: ' Golden Olive',
    RGB_COLOR: ' #9c7230'
  },
  {
    DMC_COLOR: '777',
    COLOR_NAME: ' Red - DEEP',
    RGB_COLOR: ' #9b0042'
  },
  {
    DMC_COLOR: '833',
    COLOR_NAME: ' Golden Olive - LT',
    RGB_COLOR: ' #b99956'
  },
  {
    DMC_COLOR: '778',
    COLOR_NAME: ' Antique Mauve - VY LT',
    RGB_COLOR: ' #dca6a4'
  },
  {
    DMC_COLOR: '834',
    COLOR_NAME: ' Golden Olive - VY LT',
    RGB_COLOR: ' #d2b468'
  },
  {
    DMC_COLOR: '779',
    COLOR_NAME: ' Brown',
    RGB_COLOR: ' #53332d'
  },
  {
    DMC_COLOR: '838',
    COLOR_NAME: ' Beige Brown - VY DK',
    RGB_COLOR: ' #4a3021'
  },
  {
    DMC_COLOR: '780',
    COLOR_NAME: ' Topaz - ULT VY DK',
    RGB_COLOR: ' #945026'
  },
  {
    DMC_COLOR: '839',
    COLOR_NAME: ' Beige Brown - DK',
    RGB_COLOR: ' #5a3c2d'
  },
  {
    DMC_COLOR: '781',
    COLOR_NAME: ' Topaz - VY DK',
    RGB_COLOR: ' #a25f1f'
  },
  {
    DMC_COLOR: '840',
    COLOR_NAME: ' Beige Brown - MED',
    RGB_COLOR: ' #7a5939'
  },
  {
    DMC_COLOR: '782',
    COLOR_NAME: ' Topaz - DK',
    RGB_COLOR: ' #b26923'
  },
  {
    DMC_COLOR: '841',
    COLOR_NAME: ' Beige Brown - LT',
    RGB_COLOR: ' #a37d64'
  },
  {
    DMC_COLOR: '783',
    COLOR_NAME: ' Topaz - MED',
    RGB_COLOR: ' #d0883d'
  },
  {
    DMC_COLOR: '842',
    COLOR_NAME: ' Beige Brown - VY LT',
    RGB_COLOR: ' #cbb094'
  },
  {
    DMC_COLOR: '791',
    COLOR_NAME: ' Cornflower Blue - VY DK',
    RGB_COLOR: ' #2d2068'
  },
  {
    DMC_COLOR: '844',
    COLOR_NAME: ' Beaver Gray - ULT DK',
    RGB_COLOR: ' #494842'
  },
  {
    DMC_COLOR: '792',
    COLOR_NAME: ' Cornflower Blue - DK',
    RGB_COLOR: ' #454b8b'
  },
  {
    DMC_COLOR: '868',
    COLOR_NAME: ' Hazel Nut Brown',
    RGB_COLOR: ' #995c30'
  },
  {
    DMC_COLOR: '793',
    COLOR_NAME: ' Cornflower Blue - MED',
    RGB_COLOR: ' #7c82b5'
  },
  {
    DMC_COLOR: '869',
    COLOR_NAME: ' Hazelnut Brown - VY DK',
    RGB_COLOR: ' #784c28'
  },
  {
    DMC_COLOR: '794',
    COLOR_NAME: ' Cornflower Blue - LT',
    RGB_COLOR: ' #a0b2d7'
  },
  {
    DMC_COLOR: '890',
    COLOR_NAME: ' Pistachio Green - ULT DK',
    RGB_COLOR: ' #324233'
  },
  {
    DMC_COLOR: '796',
    COLOR_NAME: ' Royal Blue - DK',
    RGB_COLOR: ' #272276'
  },
  {
    DMC_COLOR: '891',
    COLOR_NAME: ' Carnation - DK',
    RGB_COLOR: ' #ee3246'
  },
  {
    DMC_COLOR: '797',
    COLOR_NAME: ' Royal Blue',
    RGB_COLOR: ' #2b3288'
  },
  {
    DMC_COLOR: '892',
    COLOR_NAME: ' Carnation - MED',
    RGB_COLOR: ' #f44753'
  },
  {
    DMC_COLOR: '798',
    COLOR_NAME: ' Delft Blue - DK',
    RGB_COLOR: ' #4e5ca7'
  },
  {
    DMC_COLOR: '893',
    COLOR_NAME: ' Carnation - LT',
    RGB_COLOR: ' #f66879'
  },
  {
    DMC_COLOR: '799',
    COLOR_NAME: ' Delft Blue - MED',
    RGB_COLOR: ' #6b7fc0'
  },
  {
    DMC_COLOR: '894',
    COLOR_NAME: ' Carnation - VY LT',
    RGB_COLOR: ' #fd95a3'
  },
  {
    DMC_COLOR: '800',
    COLOR_NAME: ' Delft Blue - PALE',
    RGB_COLOR: ' #b5c7e9'
  },
  {
    DMC_COLOR: '895',
    COLOR_NAME: ' Hunter Green - VY DK',
    RGB_COLOR: ' #344b2e'
  },
  {
    DMC_COLOR: '801',
    COLOR_NAME: ' Coffee Brown - DK',
    RGB_COLOR: ' #60391d'
  },
  {
    DMC_COLOR: '898',
    COLOR_NAME: ' Coffee Brown - VY DK',
    RGB_COLOR: ' #532f1b'
  },
  {
    DMC_COLOR: '899',
    COLOR_NAME: ' Rose - MED',
    RGB_COLOR: ' #ea6b78'
  },
  {
    DMC_COLOR: '955',
    COLOR_NAME: ' Nile Green - LT',
    RGB_COLOR: ' #a8ebad'
  },
  {
    DMC_COLOR: '900',
    COLOR_NAME: ' Burnt Orange - DK',
    RGB_COLOR: ' #c63117'
  },
  {
    DMC_COLOR: '956',
    COLOR_NAME: ' Geranium',
    RGB_COLOR: ' #f7566d'
  },
  {
    DMC_COLOR: '902',
    COLOR_NAME: ' Garnet - VY DK',
    RGB_COLOR: ' #651329'
  },
  {
    DMC_COLOR: '957',
    COLOR_NAME: ' Geranium - PALE',
    RGB_COLOR: ' #fd99af'
  },
  {
    DMC_COLOR: '904',
    COLOR_NAME: ' Parrot Green - VY DK',
    RGB_COLOR: ' #386324'
  },
  {
    DMC_COLOR: '958',
    COLOR_NAME: ' Seagreen - DK',
    RGB_COLOR: ' #0db294'
  },
  {
    DMC_COLOR: '905',
    COLOR_NAME: ' Parrot Green - DK',
    RGB_COLOR: ' #467924'
  },
  {
    DMC_COLOR: '959',
    COLOR_NAME: ' Seagreen - MED',
    RGB_COLOR: ' #72d0b7'
  },
  {
    DMC_COLOR: '906',
    COLOR_NAME: ' Parrot Green - MED',
    RGB_COLOR: ' #6c9e29'
  },
  {
    DMC_COLOR: '961',
    COLOR_NAME: ' Dusty Rose - DK',
    RGB_COLOR: ' #de586c'
  },
  {
    DMC_COLOR: '907',
    COLOR_NAME: ' Parrot Green - LT',
    RGB_COLOR: ' #9dc72d'
  },
  {
    DMC_COLOR: '962',
    COLOR_NAME: ' Dusty Rose - MED',
    RGB_COLOR: ' #eb7183'
  },
  {
    DMC_COLOR: '909',
    COLOR_NAME: ' Emerald Green - VY DK',
    RGB_COLOR: ' #106b43'
  },
  {
    DMC_COLOR: '963',
    COLOR_NAME: ' Dusty Rose - ULT VY LT',
    RGB_COLOR: ' #fdccd1'
  },
  {
    DMC_COLOR: '910',
    COLOR_NAME: ' Emerald Green - DK',
    RGB_COLOR: ' #10814e'
  },
  {
    DMC_COLOR: '964',
    COLOR_NAME: ' Seagreen - LT',
    RGB_COLOR: ' #a5e4d4'
  },
  {
    DMC_COLOR: '911',
    COLOR_NAME: ' Emerald Green - MED',
    RGB_COLOR: ' #109256'
  },
  {
    DMC_COLOR: '966',
    COLOR_NAME: ' Baby Green - MED',
    RGB_COLOR: ' #94d28a'
  },
  {
    DMC_COLOR: '912',
    COLOR_NAME: ' Emerald Green - LT',
    RGB_COLOR: ' #36b26b'
  },
  {
    DMC_COLOR: '967',
    COLOR_NAME: ' Peach - LT',
    RGB_COLOR: ' #ffc2ac'
  },
  {
    DMC_COLOR: '913',
    COLOR_NAME: ' Nile Green - MED',
    RGB_COLOR: ' #55ca7d'
  },
  {
    DMC_COLOR: '970',
    COLOR_NAME: ' Pumpkin - LT',
    RGB_COLOR: ' #fb6721'
  },
  {
    DMC_COLOR: '915',
    COLOR_NAME: ' Plum - DK',
    RGB_COLOR: ' #95085a'
  },
  {
    DMC_COLOR: '971',
    COLOR_NAME: ' Pumpkin',
    RGB_COLOR: ' #fc670d'
  },
  {
    DMC_COLOR: '917',
    COLOR_NAME: ' Plum - MED',
    RGB_COLOR: ' #ac1071'
  },
  {
    DMC_COLOR: '972',
    COLOR_NAME: ' Canary - DEEP',
    RGB_COLOR: ' #fb9f11'
  },
  {
    DMC_COLOR: '918',
    COLOR_NAME: ' Red Copper - DK',
    RGB_COLOR: ' #883630'
  },
  {
    DMC_COLOR: '973',
    COLOR_NAME: ' Canary - BRIGHT',
    RGB_COLOR: ' #fccd2d'
  },
  {
    DMC_COLOR: '919',
    COLOR_NAME: ' Red Copper',
    RGB_COLOR: ' #9b371b'
  },
  {
    DMC_COLOR: '975',
    COLOR_NAME: ' Golden Brown - DK',
    RGB_COLOR: ' #813c11'
  },
  {
    DMC_COLOR: '920',
    COLOR_NAME: ' Copper - MED',
    RGB_COLOR: ' #ab4836'
  },
  {
    DMC_COLOR: '976',
    COLOR_NAME: ' Golden Brown - MED',
    RGB_COLOR: ' #cf7532'
  },
  {
    DMC_COLOR: '921',
    COLOR_NAME: ' Copper',
    RGB_COLOR: ' #c0573d'
  },
  {
    DMC_COLOR: '977',
    COLOR_NAME: ' Golden Brown - LT',
    RGB_COLOR: ' #ec8f43'
  },
  {
    DMC_COLOR: '922',
    COLOR_NAME: ' Copper - LT',
    RGB_COLOR: ' #dd6e4c'
  },
  {
    DMC_COLOR: '986',
    COLOR_NAME: ' Forest Green - VY DK',
    RGB_COLOR: ' #2e5230'
  },
  {
    DMC_COLOR: '924',
    COLOR_NAME: ' Gray Green - VY DK',
    RGB_COLOR: ' #384a4a'
  },
  {
    DMC_COLOR: '987',
    COLOR_NAME: ' Forest Green - DK',
    RGB_COLOR: ' #436838'
  },
  {
    DMC_COLOR: '926',
    COLOR_NAME: ' Gray Green - MED',
    RGB_COLOR: ' #617674'
  },
  {
    DMC_COLOR: '988',
    COLOR_NAME: ' Forest Green - MED',
    RGB_COLOR: ' #66924a'
  },
  {
    DMC_COLOR: '927',
    COLOR_NAME: ' Gray Green - LT',
    RGB_COLOR: ' #9fa8a5'
  },
  {
    DMC_COLOR: '989',
    COLOR_NAME: ' Forest Green',
    RGB_COLOR: ' #71a74e'
  },
  {
    DMC_COLOR: '928',
    COLOR_NAME: ' Gray Green - VY LT',
    RGB_COLOR: ' #c0c6c0'
  },
  {
    DMC_COLOR: '991',
    COLOR_NAME: ' Aquamarine - DK',
    RGB_COLOR: ' #135f55'
  },
  {
    DMC_COLOR: '930',
    COLOR_NAME: ' Antique Blue - DK',
    RGB_COLOR: ' #495c6b'
  },
  {
    DMC_COLOR: '992',
    COLOR_NAME: ' Aquamarine - LT',
    RGB_COLOR: ' #42b59e'
  },
  {
    DMC_COLOR: '931',
    COLOR_NAME: ' Antique Blue - MED',
    RGB_COLOR: ' #667684'
  },
  {
    DMC_COLOR: '993',
    COLOR_NAME: ' Aquamarine - VY LT',
    RGB_COLOR: ' #62d8b6'
  },
  {
    DMC_COLOR: '932',
    COLOR_NAME: ' Antique Blue - LT',
    RGB_COLOR: ' #93a0af'
  },
  {
    DMC_COLOR: '995',
    COLOR_NAME: ' Electric Blue - DK',
    RGB_COLOR: ' #0061b0'
  },
  {
    DMC_COLOR: '934',
    COLOR_NAME: ' Avocado Green - BLACK',
    RGB_COLOR: ' #323324'
  },
  {
    DMC_COLOR: '996',
    COLOR_NAME: ' Electric Blue - MED',
    RGB_COLOR: ' #49a8eb'
  },
  {
    DMC_COLOR: '935',
    COLOR_NAME: ' Avocado Green - DK',
    RGB_COLOR: ' #383a2a'
  },
  {
    DMC_COLOR: '3011',
    COLOR_NAME: ' Khaki Green - DK',
    RGB_COLOR: ' #655935'
  },
  {
    DMC_COLOR: '936',
    COLOR_NAME: ' Avocado Green - VY DK',
    RGB_COLOR: ' #3f4227'
  },
  {
    DMC_COLOR: '3012',
    COLOR_NAME: ' Khaki Green - MED',
    RGB_COLOR: ' #8b7b4e'
  },
  {
    DMC_COLOR: '937',
    COLOR_NAME: ' Avocado Green - MED',
    RGB_COLOR: ' #434f2c'
  },
  {
    DMC_COLOR: '3013',
    COLOR_NAME: ' Khaki Green - LT',
    RGB_COLOR: ' #afa97b'
  },
  {
    DMC_COLOR: '938',
    COLOR_NAME: ' Coffee Brown - ULT DK',
    RGB_COLOR: ' #45271a'
  },
  {
    DMC_COLOR: '3021',
    COLOR_NAME: ' Brown Gray - VY DK',
    RGB_COLOR: ' #50403b'
  },
  {
    DMC_COLOR: '939',
    COLOR_NAME: ' Blue - VY DK',
    RGB_COLOR: ' #09092f'
  },
  {
    DMC_COLOR: '3022',
    COLOR_NAME: ' Brown Gray - MED',
    RGB_COLOR: ' #848274'
  },
  {
    DMC_COLOR: '943',
    COLOR_NAME: ' Aquamarine - MED',
    RGB_COLOR: ' #009a77'
  },
  {
    DMC_COLOR: '3023',
    COLOR_NAME: ' Brown Gray - LT',
    RGB_COLOR: ' #a29b86'
  },
  {
    DMC_COLOR: '945',
    COLOR_NAME: ' Tawny',
    RGB_COLOR: ' #f6c19a'
  },
  {
    DMC_COLOR: '3024',
    COLOR_NAME: ' Brown Gray - VY LT',
    RGB_COLOR: ' #beb8ac'
  },
  {
    DMC_COLOR: '946',
    COLOR_NAME: ' Burnt Orange - MED',
    RGB_COLOR: ' #ed4115'
  },
  {
    DMC_COLOR: '3031',
    COLOR_NAME: ' Mocha Brown - VY DK',
    RGB_COLOR: ' #423014'
  },
  {
    DMC_COLOR: '947',
    COLOR_NAME: ' Burnt Orange',
    RGB_COLOR: ' #fc4f16'
  },
  {
    DMC_COLOR: '3032',
    COLOR_NAME: ' Mocha Brown - MED',
    RGB_COLOR: ' #9d8868'
  },
  {
    DMC_COLOR: '948',
    COLOR_NAME: ' Peach - VY LT',
    RGB_COLOR: ' #fde6d3'
  },
  {
    DMC_COLOR: '3033',
    COLOR_NAME: ' Mocha Brown - VY LT',
    RGB_COLOR: ' #dbc7ad'
  },
  {
    DMC_COLOR: '950',
    COLOR_NAME: ' Desert Sand - LT',
    RGB_COLOR: ' #e5ac8d'
  },
  {
    DMC_COLOR: '3041',
    COLOR_NAME: ' Antique Violet - MED',
    RGB_COLOR: ' #866a76'
  },
  {
    DMC_COLOR: '951',
    COLOR_NAME: ' Tawny - LT',
    RGB_COLOR: ' #faddb6'
  },
  {
    DMC_COLOR: '3042',
    COLOR_NAME: ' Antique Violet - LT',
    RGB_COLOR: ' #af98a0'
  },
  {
    DMC_COLOR: '954',
    COLOR_NAME: ' Nile Green',
    RGB_COLOR: ' #6fda8a'
  },
  {
    DMC_COLOR: '3045',
    COLOR_NAME: ' Yellow Beige - DK',
    RGB_COLOR: ' #af8152'
  },
  {
    DMC_COLOR: '3046',
    COLOR_NAME: ' Yellow Beige - MED',
    RGB_COLOR: ' #ceb074'
  },
  {
    DMC_COLOR: '3731',
    COLOR_NAME: ' Dusty Rose - VY DK',
    RGB_COLOR: ' #c34c5c'
  },
  {
    DMC_COLOR: '3047',
    COLOR_NAME: ' Yellow Beige - LT',
    RGB_COLOR: ' #ead8ab'
  },
  {
    DMC_COLOR: '3733',
    COLOR_NAME: ' Dusty Rose',
    RGB_COLOR: ' #ea7e86'
  },
  {
    DMC_COLOR: '3051',
    COLOR_NAME: ' Green Gray - DK',
    RGB_COLOR: ' #4c4c1e'
  },
  {
    DMC_COLOR: '3740',
    COLOR_NAME: ' Antique Violet - DK',
    RGB_COLOR: ' #71535d'
  },
  {
    DMC_COLOR: '3052',
    COLOR_NAME: ' Green Gray - MED',
    RGB_COLOR: ' #787e5c'
  },
  {
    DMC_COLOR: '3743',
    COLOR_NAME: ' Antique Violet - VY LT',
    RGB_COLOR: ' #cfc2c9'
  },
  {
    DMC_COLOR: '3053',
    COLOR_NAME: ' Green Gray',
    RGB_COLOR: ' #999d75'
  },
  {
    DMC_COLOR: '3746',
    COLOR_NAME: ' Blue Violet - DK',
    RGB_COLOR: ' #844ab5'
  },
  {
    DMC_COLOR: '3064',
    COLOR_NAME: ' Desert Sand',
    RGB_COLOR: ' #ba7056'
  },
  {
    DMC_COLOR: '3747',
    COLOR_NAME: ' Blue Violet - VY LT',
    RGB_COLOR: ' #d0c5ec'
  },
  {
    DMC_COLOR: '3072',
    COLOR_NAME: ' Beaver Gray - VY LT',
    RGB_COLOR: ' #d2d2ca'
  },
  {
    DMC_COLOR: '3750',
    COLOR_NAME: ' Antique Blue - VY DK',
    RGB_COLOR: ' #1d4552'
  },
  {
    DMC_COLOR: '3078',
    COLOR_NAME: ' Golden Yellow - VY LT',
    RGB_COLOR: ' #fcf6b6'
  },
  {
    DMC_COLOR: '3752',
    COLOR_NAME: ' Antique Blue - VY LT',
    RGB_COLOR: ' #bac9cc'
  },
  {
    DMC_COLOR: '3325',
    COLOR_NAME: ' Baby Blue - LT',
    RGB_COLOR: ' #adcde7'
  },
  {
    DMC_COLOR: '3753',
    COLOR_NAME: ' Antique Blue - ULT VY LT',
    RGB_COLOR: ' #d9e6ec'
  },
  {
    DMC_COLOR: '3326',
    COLOR_NAME: ' Rose - LT',
    RGB_COLOR: ' #f9979c'
  },
  {
    DMC_COLOR: '3755',
    COLOR_NAME: ' Baby Blue (?)',
    RGB_COLOR: ' #81a5d8'
  },
  {
    DMC_COLOR: '3328',
    COLOR_NAME: ' Salmon - DK',
    RGB_COLOR: ' #be444a'
  },
  {
    DMC_COLOR: '3756',
    COLOR_NAME: ' Baby Blue',
    RGB_COLOR: ' #e9f4fa'
  },
  {
    DMC_COLOR: '3340',
    COLOR_NAME: ' Apricot - MED',
    RGB_COLOR: ' #fd6b4f'
  },
  {
    DMC_COLOR: '3760',
    COLOR_NAME: ' Wedgewood - MED',
    RGB_COLOR: ' #467293'
  },
  {
    DMC_COLOR: '3341',
    COLOR_NAME: ' Apricot',
    RGB_COLOR: ' #fd8e78'
  },
  {
    DMC_COLOR: '3761',
    COLOR_NAME: ' Sky Blue - LT',
    RGB_COLOR: ' #b1d0df'
  },
  {
    DMC_COLOR: '3345',
    COLOR_NAME: ' Hunter Green - DK',
    RGB_COLOR: ' #40552e'
  },
  {
    DMC_COLOR: '3765',
    COLOR_NAME: ' Peacock Blue - VY DK',
    RGB_COLOR: ' #175e78'
  },
  {
    DMC_COLOR: '3346',
    COLOR_NAME: ' Hunter Green',
    RGB_COLOR: ' #56743b'
  },
  {
    DMC_COLOR: '3766',
    COLOR_NAME: ' Peacock Blue - LT',
    RGB_COLOR: ' #4b8aa1'
  },
  {
    DMC_COLOR: '3347',
    COLOR_NAME: ' Yellow Green - MED',
    RGB_COLOR: ' #6d9646'
  },
  {
    DMC_COLOR: '3768',
    COLOR_NAME: ' Gray Green - DK',
    RGB_COLOR: ' #4c605f'
  },
  {
    DMC_COLOR: '3348',
    COLOR_NAME: ' Yellow Green - LT',
    RGB_COLOR: ' #bedf74'
  },
  {
    DMC_COLOR: '3770',
    COLOR_NAME: ' Tawny - VY LT',
    RGB_COLOR: ' #fef1d8'
  },
  {
    DMC_COLOR: '3350',
    COLOR_NAME: ' Dusty Rose - ULT DK',
    RGB_COLOR: ' #aa3949'
  },
  {
    DMC_COLOR: '3771',
    COLOR_NAME: ' Peach - DK',
    RGB_COLOR: ' #e8ac9b'
  },
  {
    DMC_COLOR: '3354',
    COLOR_NAME: ' Dusty Rose - LT',
    RGB_COLOR: ' #efa5ac'
  },
  {
    DMC_COLOR: '3772',
    COLOR_NAME: ' Desert Sand - VY DK',
    RGB_COLOR: ' #995744'
  },
  {
    DMC_COLOR: '3362',
    COLOR_NAME: ' Pine Green - DK',
    RGB_COLOR: ' #49523c'
  },
  {
    DMC_COLOR: '3773',
    COLOR_NAME: ' Desert Sand - MED',
    RGB_COLOR: ' #cf866d'
  },
  {
    DMC_COLOR: '3363',
    COLOR_NAME: ' Pine Green - MED',
    RGB_COLOR: ' #617451'
  },
  {
    DMC_COLOR: '3774',
    COLOR_NAME: ' Desert Sand - VY LT',
    RGB_COLOR: ' #f3cfb4'
  },
  {
    DMC_COLOR: '3364',
    COLOR_NAME: ' Pine Green',
    RGB_COLOR: ' #8e9b6d'
  },
  {
    DMC_COLOR: '3776',
    COLOR_NAME: ' Mahogany - LT',
    RGB_COLOR: ' #c96444'
  },
  {
    DMC_COLOR: '3371',
    COLOR_NAME: ' Black Brown',
    RGB_COLOR: ' #36220e'
  },
  {
    DMC_COLOR: '3777',
    COLOR_NAME: ' Terra Cotta - VY DK',
    RGB_COLOR: ' #922f25'
  },
  {
    DMC_COLOR: '3607',
    COLOR_NAME: ' Plum - LT',
    RGB_COLOR: ' #d94c9d'
  },
  {
    DMC_COLOR: '3778',
    COLOR_NAME: ' Terra Cotta - LT',
    RGB_COLOR: ' #d2705c'
  },
  {
    DMC_COLOR: '3608',
    COLOR_NAME: ' Plum - VY LT',
    RGB_COLOR: ' #ec81be'
  },
  {
    DMC_COLOR: '3779',
    COLOR_NAME: ' Terra Cotta - ULT VY LT',
    RGB_COLOR: ' #f2ab95'
  },
  {
    DMC_COLOR: '3609',
    COLOR_NAME: ' Plum - ULT LT',
    RGB_COLOR: ' #f6b0df'
  },
  {
    DMC_COLOR: '3781',
    COLOR_NAME: ' Mocha Brown - DK',
    RGB_COLOR: ' #593f2b'
  },
  {
    DMC_COLOR: '3685',
    COLOR_NAME: ' Mauve - VY DK',
    RGB_COLOR: ' #79263b'
  },
  {
    DMC_COLOR: '3782',
    COLOR_NAME: ' Mocha Brown - LT',
    RGB_COLOR: ' #b69d80'
  },
  {
    DMC_COLOR: '3687',
    COLOR_NAME: ' Mauve',
    RGB_COLOR: ' #b5455d'
  },
  {
    DMC_COLOR: '3787',
    COLOR_NAME: ' Brown Gray - DK',
    RGB_COLOR: ' #62524c'
  },
  {
    DMC_COLOR: '3688',
    COLOR_NAME: ' Mauve - MED',
    RGB_COLOR: ' #dc7c86'
  },
  {
    DMC_COLOR: '3790',
    COLOR_NAME: ' Beige Gray - ULT DK',
    RGB_COLOR: ' #6d5a4b'
  },
  {
    DMC_COLOR: '3689',
    COLOR_NAME: ' Mauve - LT',
    RGB_COLOR: ' #f8bbc8'
  },
  {
    DMC_COLOR: '3799',
    COLOR_NAME: ' Pewter Gray - VY DK',
    RGB_COLOR: ' #39393d'
  },
  {
    DMC_COLOR: '3705',
    COLOR_NAME: ' Melon - DK',
    RGB_COLOR: ' #f2494f'
  },
  {
    DMC_COLOR: '3801',
    COLOR_NAME: ' Melon - VY DK',
    RGB_COLOR: ' #e4353d'
  },
  {
    DMC_COLOR: '3706',
    COLOR_NAME: ' Melon - MED',
    RGB_COLOR: ' #fd6e70'
  },
  {
    DMC_COLOR: '3802',
    COLOR_NAME: ' Antique Mauve - VY DK',
    RGB_COLOR: ' #672a33'
  },
  {
    DMC_COLOR: '3708',
    COLOR_NAME: ' Melon - LT',
    RGB_COLOR: ' #fda0ae'
  },
  {
    DMC_COLOR: '3803',
    COLOR_NAME: ' Mauve - DK',
    RGB_COLOR: ' #872a43'
  },
  {
    DMC_COLOR: '3712',
    COLOR_NAME: ' Salmon - MED',
    RGB_COLOR: ' #d95d5d'
  },
  {
    DMC_COLOR: '3804',
    COLOR_NAME: ' Cyclamen Pink - DK',
    RGB_COLOR: ' #ce2b63'
  },
  {
    DMC_COLOR: '3713',
    COLOR_NAME: ' Salmon - VY LT',
    RGB_COLOR: ' #fdd5d0'
  },
  {
    DMC_COLOR: '3805',
    COLOR_NAME: ' Cyclamen Pink',
    RGB_COLOR: ' #df3c73'
  },
  {
    DMC_COLOR: '3716',
    COLOR_NAME: ' Dusty Rose - VY LT',
    RGB_COLOR: ' #fcafb9'
  },
  {
    DMC_COLOR: '3806',
    COLOR_NAME: ' Cyclamen Pink - LT',
    RGB_COLOR: ' #f15a91'
  },
  {
    DMC_COLOR: '3721',
    COLOR_NAME: ' Shell Pink - DK',
    RGB_COLOR: ' #933b3d'
  },
  {
    DMC_COLOR: '3807',
    COLOR_NAME: ' Cornflower Blue',
    RGB_COLOR: ' #4b599e'
  },
  {
    DMC_COLOR: '3722',
    COLOR_NAME: ' Shell Pink - MED',
    RGB_COLOR: ' #a04b4c'
  },
  {
    DMC_COLOR: '3808',
    COLOR_NAME: ' Turquoise - ULT VY DK',
    RGB_COLOR: ' #03535c'
  },
  {
    DMC_COLOR: '3726',
    COLOR_NAME: ' Antique Mauve - DK',
    RGB_COLOR: ' #95565c'
  },
  {
    DMC_COLOR: '3809',
    COLOR_NAME: ' Turquoise - VY DK',
    RGB_COLOR: ' #136a75'
  },
  {
    DMC_COLOR: '3727',
    COLOR_NAME: ' Antique Mauve - LT',
    RGB_COLOR: ' #da9ea6'
  },
  {
    DMC_COLOR: '3810',
    COLOR_NAME: ' Turquoise - DK',
    RGB_COLOR: ' #2d8d98'
  },
  {
    DMC_COLOR: '3811',
    COLOR_NAME: ' Turquoise - VY LT',
    RGB_COLOR: ' #a8e2e5'
  },
  {
    DMC_COLOR: '3839',
    COLOR_NAME: ' Lavender Blue - MED',
    RGB_COLOR: ' #7a7ec5'
  },
  {
    DMC_COLOR: '3812',
    COLOR_NAME: ' Seagreen - VY DK',
    RGB_COLOR: ' #07a184'
  },
  {
    DMC_COLOR: '3840',
    COLOR_NAME: ' Lavender Blue - LT',
    RGB_COLOR: ' #b2bdea'
  },
  {
    DMC_COLOR: '3813',
    COLOR_NAME: ' Blue Green - LT',
    RGB_COLOR: ' #86c3ab'
  },
  {
    DMC_COLOR: '3841',
    COLOR_NAME: ' Baby Blue - PALE',
    RGB_COLOR: ' #d9eaf2'
  },
  {
    DMC_COLOR: '3814',
    COLOR_NAME: ' Aquamarine',
    RGB_COLOR: ' #0b8673'
  },
  {
    DMC_COLOR: '3842',
    COLOR_NAME: ' Wedgewood - DK',
    RGB_COLOR: ' #06506a'
  },
  {
    DMC_COLOR: '3815',
    COLOR_NAME: ' Celadon Green - DK',
    RGB_COLOR: ' #437259'
  },
  {
    DMC_COLOR: '3843',
    COLOR_NAME: ' Electric Blue',
    RGB_COLOR: ' #28a3de'
  },
  {
    DMC_COLOR: '3816',
    COLOR_NAME: ' Celadon Green',
    RGB_COLOR: ' #60937a'
  },
  {
    DMC_COLOR: '3844',
    COLOR_NAME: ' Bright Turquoise - DK',
    RGB_COLOR: ' #1f7fa0'
  },
  {
    DMC_COLOR: '3817',
    COLOR_NAME: ' Celadon Green - LT',
    RGB_COLOR: ' #81c6a4'
  },
  {
    DMC_COLOR: '3845',
    COLOR_NAME: ' Bright Turquoise - MED',
    RGB_COLOR: ' #2badd1'
  },
  {
    DMC_COLOR: '3818',
    COLOR_NAME: ' Emerald Green - ULT VY DK',
    RGB_COLOR: ' #005d2e'
  },
  {
    DMC_COLOR: '3846',
    COLOR_NAME: ' Bright Turquoise - LT',
    RGB_COLOR: ' #5eccec'
  },
  {
    DMC_COLOR: '3819',
    COLOR_NAME: ' Moss Green - LT',
    RGB_COLOR: ' #ccc959'
  },
  {
    DMC_COLOR: '3847',
    COLOR_NAME: ' Teal Green - DK',
    RGB_COLOR: ' #186358'
  },
  {
    DMC_COLOR: '3820',
    COLOR_NAME: ' Straw - DK',
    RGB_COLOR: ' #dba53e'
  },
  {
    DMC_COLOR: '3848',
    COLOR_NAME: ' Teal Green - MED',
    RGB_COLOR: ' #207e72'
  },
  {
    DMC_COLOR: '3821',
    COLOR_NAME: ' Straw',
    RGB_COLOR: ' #ebbb52'
  },
  {
    DMC_COLOR: '3849',
    COLOR_NAME: ' Teal Green - LT',
    RGB_COLOR: ' #35b193'
  },
  {
    DMC_COLOR: '3822',
    COLOR_NAME: ' Straw - LT',
    RGB_COLOR: ' #f7d169'
  },
  {
    DMC_COLOR: '3850',
    COLOR_NAME: ' Bright Green - DK',
    RGB_COLOR: ' #208b46'
  },
  {
    DMC_COLOR: '3823',
    COLOR_NAME: ' Yellow - ULT PALE',
    RGB_COLOR: ' #fef5cd'
  },
  {
    DMC_COLOR: '3851',
    COLOR_NAME: ' Bright Green - LT',
    RGB_COLOR: ' #61bb84'
  },
  {
    DMC_COLOR: '3824',
    COLOR_NAME: ' Apricot - LT',
    RGB_COLOR: ' #fcae99'
  },
  {
    DMC_COLOR: '3852',
    COLOR_NAME: ' Straw - VY DK',
    RGB_COLOR: ' #e3a730'
  },
  {
    DMC_COLOR: '3825',
    COLOR_NAME: ' Pumpkin - PALE',
    RGB_COLOR: ' #fea370'
  },
  {
    DMC_COLOR: '3853',
    COLOR_NAME: ' Autumn Gold - DK',
    RGB_COLOR: ' #ef8125'
  },
  {
    DMC_COLOR: '3826',
    COLOR_NAME: ' Golden Brown',
    RGB_COLOR: ' #b16633'
  },
  {
    DMC_COLOR: '3854',
    COLOR_NAME: ' Autumn Gold - MED',
    RGB_COLOR: ' #fbac56'
  },
  {
    DMC_COLOR: '3827',
    COLOR_NAME: ' Golden Brown - PALE',
    RGB_COLOR: ' #eaa664'
  },
  {
    DMC_COLOR: '3855',
    COLOR_NAME: ' Autumn Gold - LT',
    RGB_COLOR: ' #fddfa0'
  },
  {
    DMC_COLOR: '3828',
    COLOR_NAME: ' Hazelnut Brown',
    RGB_COLOR: ' #aa7c43'
  },
  {
    DMC_COLOR: '3856',
    COLOR_NAME: ' Mahogany - ULT VY LT',
    RGB_COLOR: ' #fdbe8e'
  },
  {
    DMC_COLOR: '3829',
    COLOR_NAME: ' Old Gold - VY DK',
    RGB_COLOR: ' #a7671d'
  },
  {
    DMC_COLOR: '3857',
    COLOR_NAME: ' Rosewood - DK',
    RGB_COLOR: ' #6a2f26'
  },
  {
    DMC_COLOR: '3830',
    COLOR_NAME: ' Terra Cotta',
    RGB_COLOR: ' #a94138'
  },
  {
    DMC_COLOR: '3858',
    COLOR_NAME: ' Rosewood - MED',
    RGB_COLOR: ' #803a32'
  },
  {
    DMC_COLOR: '3831',
    COLOR_NAME: ' Raspberry - DK',
    RGB_COLOR: ' #c12b52'
  },
  {
    DMC_COLOR: '3859',
    COLOR_NAME: ' Rosewood - LT',
    RGB_COLOR: ' #ba7a6c'
  },
  {
    DMC_COLOR: '3832',
    COLOR_NAME: ' Raspberry - MED',
    RGB_COLOR: ' #e36370'
  },
  {
    DMC_COLOR: '3860',
    COLOR_NAME: ' Cocoa',
    RGB_COLOR: ' #896362'
  },
  {
    DMC_COLOR: '3833',
    COLOR_NAME: ' Raspberry - LT',
    RGB_COLOR: ' #ea8b96'
  },
  {
    DMC_COLOR: '3861',
    COLOR_NAME: ' Cocoa - LT',
    RGB_COLOR: ' #ac8583'
  },
  {
    DMC_COLOR: '3834',
    COLOR_NAME: ' Grape - DK',
    RGB_COLOR: ' #6a2258'
  },
  {
    DMC_COLOR: '3862',
    COLOR_NAME: ' Mocha Beige - DK',
    RGB_COLOR: ' #6e492a'
  },
  {
    DMC_COLOR: '3835',
    COLOR_NAME: ' Grape - MED',
    RGB_COLOR: ' #924d78'
  },
  {
    DMC_COLOR: '3863',
    COLOR_NAME: ' Mocha Beige - MED',
    RGB_COLOR: ' #94725d'
  },
  {
    DMC_COLOR: '3836',
    COLOR_NAME: ' Grape - LT',
    RGB_COLOR: ' #c597b9'
  },
  {
    DMC_COLOR: '3864',
    COLOR_NAME: ' Mocha Beige - LT',
    RGB_COLOR: ' #c9aa92'
  },
  {
    DMC_COLOR: '3837',
    COLOR_NAME: ' Lavender - ULT DK',
    RGB_COLOR: ' #8a2a8f'
  },
  {
    DMC_COLOR: '3865',
    COLOR_NAME: ' Winter White',
    RGB_COLOR: ' #fffdf9'
  },
  {
    DMC_COLOR: '3838',
    COLOR_NAME: ' Lavender Blue - DK',
    RGB_COLOR: ' #606bad'
  },
  {
    DMC_COLOR: '3866',
    COLOR_NAME: ' Mocha Brown - ULT VY LT',
    RGB_COLOR: ' #f0e6d7'
  }
];
</script>

<style scoped>
::-webkit-scrollbar {
  width: 15px;
}
::-webkit-scrollbar-track {
  background-color: #888;
  border-radius: 5px;
}
::-webkit-scrollbar-thumb {
  background: #d6d6d6;
  border-radius: 5px;
}
::-webkit-scrollbar-thumb:hover {
  background: #f0f0f0;
}
</style>
