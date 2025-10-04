<script lang="ts">
	import { Button } from "$lib/components/ui/button/index.js";
	import * as Card from "$lib/components/ui/card/index.js";
	import { Badge } from "$lib/components/ui/badge/index.js";
	import { Input } from "$lib/components/ui/input/index.js";
	import { Textarea } from "$lib/components/ui/textarea/index.js";
	import { Label } from "$lib/components/ui/label/index.js";
	
	let mobileMenuOpen = $state(false);
	
	const services = [
		{
			title: "Desenvolvimento Web",
			description: "Criamos aplicações web modernas, escaláveis e responsivas usando as melhores tecnologias do mercado.",
			icon: "🌐"
		},
		{
			title: "Soluções Mobile",
			description: "Desenvolvemos apps nativos e híbridos que proporcionam experiências excepcionais em qualquer dispositivo.",
			icon: "📱"
		},
		{
			title: "Consultoria Tech",
			description: "Orientamos sua empresa na transformação digital com estratégias personalizadas e implementação eficiente.",
			icon: "💡"
		}
	];
	
	const benefits = [
		"Equipe especializada e experiente",
		"Metodologias ágeis",
		"Código limpo e documentado",
		"Suporte contínuo",
		"Entrega no prazo",
		"Preços competitivos"
	];
	
	const projects = [
		{
			title: "E-commerce Premium",
			category: "Varejo Digital",
			description: "Plataforma completa com gestão de estoque, pagamentos e analytics.",
			tags: ["React", "Node.js", "PostgreSQL"]
		},
		{
			title: "App de Gestão",
			category: "Produtividade",
			description: "Sistema web para gerenciamento de projetos e equipes remotas.",
			tags: ["SvelteKit", "TypeScript", "Prisma"]
		},
		{
			title: "Portal Corporativo",
			category: "Empresarial",
			description: "Intranet moderna com integração de sistemas legados.",
			tags: ["Vue.js", "Express", "MongoDB"]
		}
	];
</script>

<div class="min-h-screen bg-background">
	<!-- Header -->
	<header class="sticky top-0 z-50 w-full border-b border-border bg-background/95 backdrop-blur supports-[backdrop-filter]:bg-background/60">
		<div class="container mx-auto px-4 sm:px-6 lg:px-8">
			<div class="flex h-16 items-center justify-between">
				<div class="flex items-center gap-2">
					<div class="flex h-10 w-10 items-center justify-center rounded-lg bg-primary">
						<span class="text-xl font-bold text-primary-foreground">D</span>
					</div>
					<span class="text-xl font-bold text-foreground">Dunas Lab</span>
				</div>
				
				<!-- Desktop Navigation -->
				<nav class="hidden md:flex items-center gap-6">
					<a href="#servicos" class="text-sm font-medium text-muted-foreground hover:text-foreground transition-colors">Serviços</a>
					<a href="#projetos" class="text-sm font-medium text-muted-foreground hover:text-foreground transition-colors">Projetos</a>
					<a href="#sobre" class="text-sm font-medium text-muted-foreground hover:text-foreground transition-colors">Sobre</a>
					<a href="#contato" class="text-sm font-medium text-muted-foreground hover:text-foreground transition-colors">Contato</a>
					<Button href="#contato">Começar Projeto</Button>
				</nav>
				
				<!-- Mobile Menu Button -->
				<button 
					class="md:hidden p-2 hover:bg-accent rounded-md transition-colors"
					onclick={() => mobileMenuOpen = !mobileMenuOpen}
					aria-label="Toggle menu"
				>
					{#if mobileMenuOpen}
						<svg class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
							<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
						</svg>
					{:else}
						<svg class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
							<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
						</svg>
					{/if}
				</button>
			</div>
		</div>
		
		<!-- Mobile Navigation -->
		{#if mobileMenuOpen}
			<nav class="md:hidden border-t border-border bg-background px-4 py-4">
				<div class="flex flex-col gap-4">
					<a href="#servicos" class="text-sm font-medium text-muted-foreground hover:text-foreground transition-colors" onclick={() => mobileMenuOpen = false}>Serviços</a>
					<a href="#projetos" class="text-sm font-medium text-muted-foreground hover:text-foreground transition-colors" onclick={() => mobileMenuOpen = false}>Projetos</a>
					<a href="#sobre" class="text-sm font-medium text-muted-foreground hover:text-foreground transition-colors" onclick={() => mobileMenuOpen = false}>Sobre</a>
					<a href="#contato" class="text-sm font-medium text-muted-foreground hover:text-foreground transition-colors" onclick={() => mobileMenuOpen = false}>Contato</a>
					<Button href="#contato" class="w-full" onclick={() => mobileMenuOpen = false}>Começar Projeto</Button>
				</div>
			</nav>
		{/if}
	</header>

	<!-- Hero Section -->
	<section class="container mx-auto px-4 sm:px-6 lg:px-8 py-12 sm:py-20 lg:py-28">
		<div class="grid lg:grid-cols-2 gap-12 items-center">
			<div class="space-y-6 text-center lg:text-left">
				<Badge variant="secondary" class="text-sm">Software House em Parnaíba, PI</Badge>
				<h1 class="text-4xl sm:text-5xl lg:text-6xl font-bold tracking-tight">
					Transformamos <span class="text-primary">ideias</span> em soluções digitais
				</h1>
				<p class="text-lg sm:text-xl text-muted-foreground max-w-2xl mx-auto lg:mx-0">
					Somos uma software house especializada em criar produtos digitais inovadores que impulsionam o crescimento do seu negócio.
				</p>
				<div class="flex flex-col sm:flex-row gap-4 justify-center lg:justify-start">
					<Button size="lg" href="#contato">Solicitar Orçamento</Button>
					<Button size="lg" variant="outline" href="#projetos">Ver Projetos</Button>
				</div>
			</div>
			<div class="hidden lg:block">
				<Card.Root class="border-2">
					<Card.Content class="p-8">
						<div class="aspect-square rounded-xl bg-gradient-to-br from-primary/20 to-primary/5 flex items-center justify-center">
							<span class="text-8xl">💻</span>
						</div>
					</Card.Content>
				</Card.Root>
			</div>
		</div>
	</section>

	<!-- Services Section -->
	<section id="servicos" class="bg-muted/50 py-12 sm:py-20">
		<div class="container mx-auto px-4 sm:px-6 lg:px-8">
			<div class="text-center space-y-4 mb-12">
				<h2 class="text-3xl sm:text-4xl font-bold">Nossos Serviços</h2>
				<p class="text-lg text-muted-foreground max-w-2xl mx-auto">
					Oferecemos soluções completas para todas as necessidades do seu projeto digital
				</p>
			</div>
			
			<div class="grid sm:grid-cols-2 lg:grid-cols-3 gap-6 lg:gap-8">
				{#each services as service}
					<Card.Root class="hover:shadow-lg transition-shadow">
						<Card.Header>
							<div class="text-4xl mb-4">{service.icon}</div>
							<Card.Title>{service.title}</Card.Title>
						</Card.Header>
						<Card.Content>
							<Card.Description class="text-base">{service.description}</Card.Description>
						</Card.Content>
					</Card.Root>
				{/each}
			</div>
		</div>
	</section>

	<!-- Benefits Section -->
	<section class="py-12 sm:py-20">
		<div class="container mx-auto px-4 sm:px-6 lg:px-8">
			<div class="grid lg:grid-cols-2 gap-12 items-center">
				<div class="space-y-6">
					<h2 class="text-3xl sm:text-4xl font-bold">Por que escolher a Dunas Lab?</h2>
					<p class="text-lg text-muted-foreground">
						Combinamos expertise técnica com visão de negócio para entregar soluções que realmente fazem a diferença.
					</p>
					<div class="grid sm:grid-cols-2 gap-4">
						{#each benefits as benefit}
							<Card.Root>
								<Card.Content class="p-4">
									<div class="flex items-start gap-3">
										<span class="text-primary text-xl">✓</span>
										<span class="text-sm">{benefit}</span>
									</div>
								</Card.Content>
							</Card.Root>
						{/each}
					</div>
					<Button size="lg" href="#contato">Falar com Especialista</Button>
				</div>
				<Card.Root class="bg-muted">
					<Card.Content class="p-8 lg:p-12 space-y-8">
						<div class="space-y-2">
							<div class="text-4xl sm:text-5xl font-bold text-primary">50+</div>
							<div class="text-sm text-muted-foreground">Projetos Entregues</div>
						</div>
						<div class="space-y-2">
							<div class="text-4xl sm:text-5xl font-bold text-primary">98%</div>
							<div class="text-sm text-muted-foreground">Satisfação dos Clientes</div>
						</div>
						<div class="space-y-2">
							<div class="text-4xl sm:text-5xl font-bold text-primary">5+</div>
							<div class="text-sm text-muted-foreground">Anos de Experiência</div>
						</div>
					</Card.Content>
				</Card.Root>
			</div>
		</div>
	</section>

	<!-- Projects Section -->
	<section id="projetos" class="bg-muted/50 py-12 sm:py-20">
		<div class="container mx-auto px-4 sm:px-6 lg:px-8">
			<div class="text-center space-y-4 mb-12">
				<h2 class="text-3xl sm:text-4xl font-bold">Projetos em Destaque</h2>
				<p class="text-lg text-muted-foreground max-w-2xl mx-auto">
					Conheça alguns dos projetos que desenvolvemos com sucesso
				</p>
			</div>
			
			<div class="grid sm:grid-cols-2 lg:grid-cols-3 gap-6">
				{#each projects as project}
					<Card.Root class="overflow-hidden hover:shadow-lg transition-shadow">
						<div class="aspect-video bg-gradient-to-br from-primary/20 to-primary/5 flex items-center justify-center">
							<span class="text-6xl">🚀</span>
						</div>
						<Card.Header>
							<Badge variant="secondary" class="w-fit mb-2">{project.category}</Badge>
							<Card.Title>{project.title}</Card.Title>
							<Card.Description>{project.description}</Card.Description>
						</Card.Header>
						<Card.Content>
							<div class="flex flex-wrap gap-2">
								{#each project.tags as tag}
									<Badge variant="outline">{tag}</Badge>
								{/each}
							</div>
						</Card.Content>
					</Card.Root>
				{/each}
			</div>
		</div>
	</section>

	<!-- About Section -->
	<section id="sobre" class="py-12 sm:py-20">
		<div class="container mx-auto px-4 sm:px-6 lg:px-8">
			<div class="max-w-3xl mx-auto">
				<Card.Root>
					<Card.Header class="text-center">
						<Card.Title class="text-3xl sm:text-4xl">Sobre a Dunas Lab</Card.Title>
					</Card.Header>
					<Card.Content class="space-y-4 text-center">
						<p class="text-lg text-muted-foreground">
							Somos uma equipe apaixonada por tecnologia, dedicada a criar soluções digitais que transformam negócios. Com anos de experiência no mercado, utilizamos as tecnologias mais modernas para desenvolver produtos escaláveis, seguros e eficientes.
						</p>
						<p class="text-lg text-muted-foreground">
							Nossa missão é ser o parceiro tecnológico ideal para empresas que buscam inovação e resultados concretos no ambiente digital.
						</p>
					</Card.Content>
				</Card.Root>
			</div>
		</div>
	</section>

	<!-- Contact Section -->
	<section id="contato" class="bg-muted/50 py-12 sm:py-20">
		<div class="container mx-auto px-4 sm:px-6 lg:px-8">
			<div class="max-w-4xl mx-auto">
				<div class="text-center space-y-4 mb-12">
					<h2 class="text-3xl sm:text-4xl font-bold">Vamos Conversar?</h2>
					<p class="text-lg text-muted-foreground">
						Entre em contato e descubra como podemos ajudar seu projeto
					</p>
				</div>
				
				<div class="grid sm:grid-cols-2 gap-8">
					<Card.Root>
						<Card.Header>
							<Card.Title>Envie uma Mensagem</Card.Title>
						</Card.Header>
						<Card.Content>
							<form class="space-y-4">
								<div class="space-y-2">
									<Label for="name">Nome</Label>
									<Input id="name" type="text" placeholder="Seu nome" />
								</div>
								<div class="space-y-2">
									<Label for="email">E-mail</Label>
									<Input id="email" type="email" placeholder="seu@email.com" />
								</div>
								<div class="space-y-2">
									<Label for="message">Mensagem</Label>
									<Textarea id="message" rows={4} placeholder="Conte-nos sobre seu projeto..." />
								</div>
								<Button type="submit" class="w-full" size="lg">Enviar Mensagem</Button>
							</form>
						</Card.Content>
					</Card.Root>
					
					<div class="space-y-6">
						<Card.Root>
							<Card.Header>
								<Card.Title>Informações de Contato</Card.Title>
							</Card.Header>
							<Card.Content class="space-y-4">
								<div class="flex items-start gap-3">
									<span class="text-primary text-xl">📧</span>
									<div class="space-y-1">
										<div class="text-sm font-medium">E-mail</div>
										<a href="mailto:contato@dunaslab.com" class="text-sm text-muted-foreground hover:text-primary">contato@dunaslab.com</a>
									</div>
								</div>
								<div class="flex items-start gap-3">
									<span class="text-primary text-xl">📱</span>
									<div class="space-y-1">
										<div class="text-sm font-medium">Telefone</div>
										<a href="tel:+5586999999999" class="text-sm text-muted-foreground hover:text-primary">(86) 99999-9999</a>
									</div>
								</div>
								<div class="flex items-start gap-3">
									<span class="text-primary text-xl">📍</span>
									<div class="space-y-1">
										<div class="text-sm font-medium">Localização</div>
										<div class="text-sm text-muted-foreground">Parnaíba, Piauí, Brasil</div>
									</div>
								</div>
							</Card.Content>
						</Card.Root>
						
						<Card.Root>
							<Card.Header>
								<Card.Title class="text-lg">Horário de Atendimento</Card.Title>
							</Card.Header>
							<Card.Content class="space-y-2 text-sm text-muted-foreground">
								<div class="flex justify-between">
									<span>Segunda - Sexta</span>
									<span>9h - 18h</span>
								</div>
								<div class="flex justify-between">
									<span>Sábado</span>
									<span>9h - 13h</span>
								</div>
							</Card.Content>
						</Card.Root>
					</div>
				</div>
			</div>
		</div>
	</section>

	<!-- Footer -->
	<footer class="border-t border-border py-8 sm:py-12">
		<div class="container mx-auto px-4 sm:px-6 lg:px-8">
			<div class="grid sm:grid-cols-2 lg:grid-cols-4 gap-8 mb-8">
				<div class="space-y-4">
					<div class="flex items-center gap-2">
						<div class="flex h-10 w-10 items-center justify-center rounded-lg bg-primary">
							<span class="text-xl font-bold text-primary-foreground">D</span>
						</div>
						<span class="text-xl font-bold">Dunas Lab</span>
					</div>
					<p class="text-sm text-muted-foreground">
						Transformando ideias em soluções digitais inovadoras.
					</p>
				</div>
				
				<div class="space-y-4">
					<h4 class="font-semibold">Serviços</h4>
					<ul class="space-y-2 text-sm text-muted-foreground">
						<li><a href="#servicos" class="hover:text-primary transition-colors">Desenvolvimento Web</a></li>
						<li><a href="#servicos" class="hover:text-primary transition-colors">Soluções Mobile</a></li>
						<li><a href="#servicos" class="hover:text-primary transition-colors">Consultoria Tech</a></li>
					</ul>
				</div>
				
				<div class="space-y-4">
					<h4 class="font-semibold">Empresa</h4>
					<ul class="space-y-2 text-sm text-muted-foreground">
						<li><a href="#sobre" class="hover:text-primary transition-colors">Sobre Nós</a></li>
						<li><a href="#projetos" class="hover:text-primary transition-colors">Projetos</a></li>
						<li><a href="#contato" class="hover:text-primary transition-colors">Contato</a></li>
					</ul>
				</div>
				
				<div class="space-y-4">
					<h4 class="font-semibold">Legal</h4>
					<ul class="space-y-2 text-sm text-muted-foreground">
						<li><a href="#" class="hover:text-primary transition-colors">Política de Privacidade</a></li>
						<li><a href="#" class="hover:text-primary transition-colors">Termos de Uso</a></li>
					</ul>
				</div>
			</div>
			
			<div class="pt-8 border-t border-border text-center text-sm text-muted-foreground">
				<p>&copy; {new Date().getFullYear()} Dunas Lab. Todos os direitos reservados.</p>
			</div>
		</div>
	</footer>
</div>