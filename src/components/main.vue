<template>
  <div class="flex items-center flex-c justify-center">
    <div class="mt-[64px] h-[500px] w-[80%] bg-[#d0c7ff] flex rounded-3xl">
      <div class="mt-[10px] w-[250px] h-[100%] flex flex-col gap-2 ml-[3px]">
        <button
          class="flex h-[52px] w-[250px] bg-slate-200 items-center text-center px-[24px] gap-3 hover:bg-slate-300"
        >
          <img
            class="w-[20px] h-[20px] transition-colors duration-300 hover:filter hover:brightness-0 hover:invert-[10%]"
            src="../../public/icons/shop.svg"
            alt=""
          />
          <p
            class="text-lg text-[#475569] font-semibold transition-colors duration-300 hover:text-[#00B5D7]"
          >
            Заказы
          </p>
        </button>

        <button
          class="flex h-[52px] w-[250px] bg-slate-200 items-center text-center px-[24px] gap-3 hover:bg-slate-300"
        >
          <img
            class="w-[20px] h-[20px] transition-colors duration-300 hover:filter hover:brightness-0 hover:invert-[10%]"
            src="../../public/icons/agreement.svg"
            alt=""
          />
          <p
            class="text-lg text-[#475569] font-semibold transition-colors duration-300 hover:text-[#00B5D7]"
          >Договора</p>
        </button>

        <button
          class="flex h-[52px] w-[250px] bg-slate-200 items-center text-center px-[24px] gap-3 hover:bg-slate-300"
        >
          <img
            class="w-[20px] h-[20px] transition-colors duration-300 hover:filter hover:brightness-0 hover:invert-[10%]"
            src="../../public/icons/Community.svg"
            alt=""
          />
          <p
            class="text-lg text-[#475569] font-semibold transition-colors duration-300 hover:text-[#00B5D7]"
          >Сообщество</p>
        </button>

        <button
          class="flex h-[52px] w-[250px] bg-slate-200 items-center text-center px-[24px] gap-3 hover:bg-slate-300"
        >
          <img
            class="w-[20px] h-[20px] transition-colors duration-300 hover:filter hover:brightness-0 hover:invert-[10%]"
            src="../../public/icons/Notification.svg"
            alt=""
          />
          <p
            class="text-lg text-[#475569] font-semibold transition-colors duration-300 hover:text-[#00B5D7]"
          >Уведомления</p>
        </button>

        <button
          class="flex h-[52px] w-[250px] bg-slate-200 items-center text-center px-[24px] gap-3 hover:bg-slate-300"
        >
         <img
            class="w-[20px] h-[20px] transition-colors duration-300 hover:filter hover:brightness-0 hover:invert-[10%]"
            src="../../public/icons/Applications.svg"
            alt=""
          />
          <p
            class="text-lg text-[#475569] font-semibold transition-colors duration-300 hover:text-[#00B5D7]"
          >Заявки</p>
        </button>

        <button
          class="flex h-[52px] w-[250px] bg-slate-200 items-center text-center px-[24px] gap-3 hover:bg-slate-300"
        >
          <img
            class="w-[20px] h-[20px] transition-colors duration-300 hover:filter hover:brightness-0 hover:invert-[10%]"
            src="../../public/icons/Favorites.svg"
            alt=""
          />
          <p
            class="text-lg text-[#475569] font-semibold transition-colors duration-300 hover:text-[#00B5D7]"
          >Избранные</p>
        </button>

        <button
          class="flex h-[52px] w-[250px] bg-slate-200 items-center text-center px-[24px] gap-3 hover:bg-slate-300"
        >
         <img
            class="w-[20px] h-[20px] transition-colors duration-300 hover:filter hover:brightness-0 hover:invert-[10%]"
            src="../../public/icons/Activity.svg"
            alt=""
          />
          <p
            class="text-lg text-[#475569] font-semibold transition-colors duration-300 hover:text-[#00B5D7]"
          >Отчеты</p>
        </button>

        <button
          class="flex h-[52px] w-[250px] bg-slate-200 items-center text-center px-[24px] gap-3 hover:bg-slate-300"
        >
          <img
            class="w-[20px] h-[20px] transition-colors duration-300 hover:filter hover:brightness-0 hover:invert-[10%]"
            src="../../public/icons/Setting.svg"
            alt=""
          />
          <p
            class="text-lg text-[#475569] font-semibold transition-colors duration-300 hover:text-[#00B5D7]"
          >Настройки</p>
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "mainVue",
};
</script>

<style scoped></style>
