<script>
	let isDark = $state(false);

	$effect(() => {
		const observer = new IntersectionObserver(
			(entries) => {
				entries.forEach((entry) => {
					if (entry.isIntersecting) {
						isDark = entry.target.classList.contains('section--dark');
					}
				});
			},
			{ threshold: 0.5 } // nur, wenn ~50% sichtbar sind
		);

		document.querySelectorAll('.section--light, .section--dark').forEach((section) => {
			observer.observe(section);
		});

		return () => observer.disconnect();
	});
</script>

<header>
	<nav class:dark={isDark}>
		<p>Minor: Projektkontor</p>
		<div class="nav-btns">
			<button>Ausstellung</button>
			<button>Projektkontext</button>
			<button>Förderung</button>
			<button>Kontakt</button>
		</div>
	</nav>
</header>

<section class="hero section--dark">
	<h1>Bibliotheken als Orte der Demokratiegeschichte</h1>
	<h2>Eine partizipative Recherche von Nutzer*innen der Amerika-Gedenkbibliothek in Berlin</h2>
</section>

<div class="body">
	<section class="intro section--dark">
		<p>
			In einer partizipativen Recherche erforschen Nutzer*innen der Amerika-Gedenkbibliothek deren
			Geschichte als Ort der Demokratisierung. Ziel ist, die Rolle öffentlicher Bibliotheken als
			Foren der Meinungsbildung zu beleuchten und partizipative Prozesse zu ihrer zukünftigen
			Bedeutung als demokratische Räume anzustoßen.
		</p>
		<button>mehr zum Projekt</button>
	</section>

	<section class="projekt section--dark">
		<h1>Über das Projekt</h1>
		<h2>
			Subheading that sets up context, shares more info about the author, or generally gets people
			psyched to keep reading
		</h2>
		<img
			class="section-light"
			src="/src/lib/assets/img_projekt1.jpg"
			alt="Gruppenfoto mit ZLB im Hintergrund"
		/>
		<p>
			Die Geschichte und Rolle der Amerika-Gedenkbibliothek (AGB) als Ort der Demokratisierung über
			gesellschaftliche Grenzen hinweg wird in einem partizipativen Prozess analysiert und in einer
			digitalen Ausstellung mit historisch-politischen Bildungsbegleitprogramm veröffentlicht. Die
			Auseinandersetzung mit der AGB dient dabei auch als Ausgangspunkt für die Beschäftigung mit
			der Geschichte und Zukunft von öffentlichen Bibliotheken als Orte der Demokratie in
			Deutschland im Allgemeinen. Für dieses Citizen-Science-Projekt werden Nutzer*innen der
			Bibliothek und Einwohner*innen des Kiezes als Co-Forscher*innen einbezogen, die sehr diverse
			Erfahrungen mit und Perspektiven auf die Bibliothek einbringen. Neben der historischen
			Aufarbeitung durch die Co-Forscher*innen werden partizipative Prozesse der Auseinandersetzung
			über die zukünftige Rolle von Bibliotheken als demokratische Räume angestoßen und in Form von
			Befragungen, Workshops, Zukunftsforen und mehr erprobt. Aus den gewonnenen Erkenntnissen der
			Co-Forscher*innen wird eine digitale Ausstellung und ein historisch-politisches
			Bildungsangebot über öffentliche Bibliotheken als Orte der Reeducation und Demokratisierung am
			Beispiel der AGB erarbeitet.
		</p>

    <div class="img-carousel--2">
      <img src="/src/lib/assets/img_projekt2.jpg" alt="">
      <img src="/src/lib/assets/img_projekt3.jpg" alt="">
    </div>

    <p>Die Erinnerung an die Bedeutung der öffentlichen Bibliothek als demokratischer Raum der Meinungsbildung und des Dialoges sowie die partizipative Auseinandersetzung über ihre Zukunft sollte bundesweit angelegt und umgesetzt werden.</p>

    <p>Die Ausstellung und das Begleitprogramm werden so aufbereitet, dass sie im Anschluss auch analog fertiggestellt und in öffentlichen Bibliotheken sowie der Deutschen Nationalbibliothek mit begleitenden historisch-politischen Bildungsangeboten gezeigt werden können.</p>

	</section>

  <section class="förderung">

    <h1>gefördert & unterstützt von</h1>
    <p>Das Projekt wird gefördert durch die Stiftung „Orte der deutschen Demokratiegeschichte“.</p>
<img src="/src/lib/assets/logo_stiftung.png" alt="">
  </section>



</div>
