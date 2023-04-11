<script>
  export let response;
</script>

<div id="cards">
  <div id="cards-grid" class="grid grid-cols-2 gap-10 mb-14">
    {#each response as { cover_image, url, title, tag_list, description, user }}
      <article class="flex flex-col">
        <div class="relative">
          <img
            src={cover_image
              ? cover_image
              : "https://picsum.photos/seed/picsum/588/320"}
            alt={tag_list[0]}
            width="588"
            height="320"
            class="object-cover w-full"
          />
          <div
            class="absolute bottom-0 left-0 h-[28%] w-full backdrop-blur-md bg-white/40 border-t border-t-white flex justify-between items-center px-6 py-6"
          >
            <div class="h-full flex flex-col">
              <h3 class="text-[16px] font-bold">{user.name}</h3>
              <p class="text-[16px]">20 Jan 2022</p>
            </div>
            <div class="h-full">
              <h3 class="text-[16px] font-bold">{tag_list[0]}</h3>
            </div>
          </div>
        </div>
        <div id="card-footer">
          <br />
          <h2 class="text-2xl font-bold">{title}</h2>
          <p class="text-xl">
            {description}
          </p>
          <br />
          <a href={url} target="_blank" rel="noreferrer"
            ><span class="font-semibold text-[18px]">Read post </span>
            <svg
              width="800px"
              height="800px"
              viewBox="0 0 24 24"
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              stroke="#000000"
              stroke-width="2"
              stroke-linecap="round"
              stroke-linejoin="round"
              class="feather feather-arrow-up-right h-5 w-5 inline-block"
              ><line x1="7" y1="17" x2="17" y2="7" /><polyline
                points="7 7 17 7 17 17"
              /></svg
            >
          </a>
        </div>
      </article>
    {/each}
  </div>
  <div class="text-center mb-20">
    <button class="rounded-full bg-blue-950 text-white py-3 px-8"
      ><span class="font-semibold font-lg">Load More</span></button
    >
  </div>
</div>
