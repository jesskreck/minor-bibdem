<script lang="ts">
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

	function scrollToSection(sectionId: string) {
		const element = document.getElementById(sectionId);
		if (element) {
			element.scrollIntoView({ behavior: 'smooth' });
		}
	}

	function openContactEmail() {
		const subject = encodeURIComponent('Anfrage zu: Bibliotheken als Orte der Demokratiegeschichte');
		const body = encodeURIComponent('Hallo,\n\nich habe die Webseite zum Projekt "Bibliotheken als Orte der Demokratiegeschichte" gesehen und habe folgende Frage:\n\nViele Grüße');
		window.location.href = `mailto:a.oswald@minor-kontor.de?subject=${subject}&body=${body}`;
	}

	function openModal(modalId: string) {
   const modal = document.getElementById(modalId) as HTMLDialogElement;
   if (modal) {
   	modal.showModal();
   	
   	// Click outside schließt Modal
   	modal.addEventListener('click', (e) => {
   		if (e.target === modal) {
   			modal.close();
   		}
   	}, { once: true });
   }
}
</script>

<header>
	<nav class:dark={isDark}>
		<p>Minor: Projektkontor</p>
		<div class="nav-btns">
			<button onclick={() => scrollToSection('ausstellung')}>Ausstellung</button>
			<button onclick={() => scrollToSection('projektkontext')}>Projektkontext</button>
			<button onclick={() => scrollToSection('förderung')}>Förderung</button>
			<button onclick={openContactEmail}>Kontakt</button>
		</div>
	</nav>
</header>

<section class="hero section--dark">
	<h1>Bibliotheken als Orte der Demokratiegeschichte</h1>
	<h3>Eine partizipative Recherche von Nutzer*innen der Amerika-Gedenkbibliothek in Berlin</h3>
</section>

<div class="body">
	<section class="intro section--dark">
		<p>
			In einer partizipativen Recherche erforschen Nutzer*innen der Amerika-Gedenkbibliothek deren
			Geschichte als Ort der Demokratisierung. Ziel ist, die Rolle öffentlicher Bibliotheken als
			Foren der Meinungsbildung zu beleuchten und partizipative Prozesse zu ihrer zukünftigen
			Bedeutung als demokratische Räume anzustoßen.
		</p>
		<button onclick={() => scrollToSection('projektkontext')}>mehr zum Projekt</button>
	</section>

	<section class="ausstellung section--dark" id="ausstellung">
		<h1>Ausstellungseinheiten</h1>

		<div class="grid-einheiten">
			<img src="/einheit1.jpg" alt="" />
			<div>
				<h2>Die AGB gestern und heute</h2>
				<p>A subheading for this section, as long or as short as you like</p>
				<button onclick={() => openModal('modal-block1')}>Einheiten Block 1</button>
			</div>
		</div>

		<div class="grid-einheiten">
			<img src="/einheit2.png" alt="" />
			<div>
				<h2>Die AGB als Symbol der amerikanischen Reeducationing</h2>
				<p>A subheading for this section, as long or as short as you like</p>
				<button onclick={() => openModal('modal-block2')}>Einheiten Block 2</button>
			</div>
		</div>

		<div class="grid-einheiten">
			<img src="/einheit3.png" alt="" />
			<div>
				<h2>Demokratische Auseinandersetzungen</h2>
				<p>A subheading for this section, as long or as short as you like</p>
				<button onclick={() => openModal('modal-block3')}>Einheiten Block 3</button>
			</div>
		</div>

		<div class="grid-einheiten">
			<img src="/einheit4.png" alt="" />
			<div>
				<h2>Bibliothek für Alle?</h2>
				<p>A subheading for this section, as long or as short as you like</p>
				<button onclick={() => openModal('modal-block4')}>Einheiten Block 4</button>
			</div>
		</div>
	</section>

	<section class="projekt section--dark" id="projektkontext">
		<h1>Über das Projekt</h1>
		<h3>
			Subheading that sets up context, shares more info about the author, or generally gets people
			psyched to keep reading
		</h3>
		<img
			class="section-light"
			src="/img_projekt1.jpg"
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
			<img src="/img_projekt2.jpg" alt="" />
			<img src="/img_projekt3.jpg" alt="" />
		</div>

		<p>
			Die Erinnerung an die Bedeutung der öffentlichen Bibliothek als demokratischer Raum der
			Meinungsbildung und des Dialoges sowie die partizipative Auseinandersetzung über ihre Zukunft
			sollte bundesweit angelegt und umgesetzt werden.
		</p>

		<p>
			Die Ausstellung und das Begleitprogramm werden so aufbereitet, dass sie im Anschluss auch
			analog fertiggestellt und in öffentlichen Bibliotheken sowie der Deutschen Nationalbibliothek
			mit begleitenden historisch-politischen Bildungsangeboten gezeigt werden können.
		</p>
	</section>

	<section class="förderung" id="förderung">
		<h1>gefördert & unterstützt von</h1>
		<p>Das Projekt wird gefördert durch die Stiftung „Orte der deutschen Demokratiegeschichte“.</p>
		<img src="/logo_stiftung.png" alt="" />
	</section>
</div>



<dialog id="modal-block1" class="modal">
  <div class="modal-box">
	<h1>Platzhalter Block 1</h1>
    <h3 class="text-lg font-bold">Hello!</h3>
    <p class="py-4">Press ESC key or click outside to close</p>
  </div>
  <form method="dialog" class="modal-backdrop">
    <button>close</button>
  </form>
</dialog>


<dialog id="modal-block2" class="modal">
  <div class="modal-box">
		<h1>Platzhalter Block 2</h1>

    <h3 class="text-lg font-bold">Hello!</h3>
    <p class="py-4">Press ESC key or click outside to close</p>
  </div>
  <form method="dialog" class="modal-backdrop">
    <button>close</button>
  </form>
</dialog>


<dialog id="modal-block3" class="modal">
  <div class="modal-box">
		<h1>Platzhalter Block 3</h1>

    <h3 class="text-lg font-bold">Hello!</h3>
    <p class="py-4">Press ESC key or click outside to close</p>
  </div>
  <form method="dialog" class="modal-backdrop">
    <button>close</button>
  </form>
</dialog>


<dialog id="modal-block4" class="modal">
  <div class="modal-box">
		<h1>Platzhalter Block 4</h1>

    <h3 class="text-lg font-bold">Hello!</h3>
    <p class="py-4">Press ESC key or click outside to close</p>
  </div>
  <form method="dialog" class="modal-backdrop">
    <button>close</button>
  </form>
</dialog>