## <a name="integration-models-for-solution-providers"></a><span data-ttu-id="2c800-101">Modèles d’intégration pour les fournisseurs de solutions</span><span class="sxs-lookup"><span data-stu-id="2c800-101">Integration models for solution providers</span></span>

<a name="steps"></a>

<span data-ttu-id="2c800-102">En tant que fournisseur de solutions de centre de contacts, vous avez le choix entre trois modèles pour intégrer votre solution de centre de contacts connecté dans Teams :</span><span class="sxs-lookup"><span data-stu-id="2c800-102">As a contact center solution provider, there are three models to choose from to integrate your connected contact center solution into Teams:</span></span>

- <span data-ttu-id="2c800-103">Si vous voulez utiliser des SBCs certifiés et un routage direct pour connecter une solution de centre de contacts à Teams, consultez [le modèle Connect.](?tabs=connect#steps)</span><span class="sxs-lookup"><span data-stu-id="2c800-103">If you want to use certified SBCs and Direct Routing to connect a contact center solution to Teams, see the [Connect model](?tabs=connect#steps).</span></span>

- <span data-ttu-id="2c800-104">Si vous voulez utiliser des robots Azure et les API de communication De Microsoft Graph pour permettre aux fournisseurs de solutions de créer des applications Teams, consultez [le modèle Étendre.](?tabs=extend#steps)</span><span class="sxs-lookup"><span data-stu-id="2c800-104">If you want to use Azure bots and the Microsoft Graph Communication APIs to enable solution providers to create Teams apps, see the [Extend model](?tabs=extend#steps).</span></span>

- <span data-ttu-id="2c800-105">Si vous voulez utiliser un SDK qui permet aux fournisseurs de solutions d’imbed les expériences Teams natives dans leur application, consultez [le modèle Power.](?tabs=power#steps)</span><span class="sxs-lookup"><span data-stu-id="2c800-105">If you want to use an SDK that enables solution providers to imbed native Teams experiences in their App, see the [Power model](?tabs=power#steps).</span></span> <span data-ttu-id="2c800-106">Les solutions Power Seront possibles lorsque le SDK sera disponible, vers la fin de l’année 2021.</span><span class="sxs-lookup"><span data-stu-id="2c800-106">Power solutions will be possible when the SDK is available, towards the end of 2021.</span></span>

### <a name="the-connect-model"></a>[<span data-ttu-id="2c800-107">**Le modèle Connecter**</span><span class="sxs-lookup"><span data-stu-id="2c800-107">**The Connect model**</span></span>](#tab/connect)

<span data-ttu-id="2c800-108">Le modèle Connect utilise les SBCs certifiés Microsoft et le routage direct pour connecter les solutions du centre de contacts à l’infrastructure du système téléphonique de Teams, ce qui permet d’améliorer le routage, la configuration et les informations système.</span><span class="sxs-lookup"><span data-stu-id="2c800-108">The Connect model uses Microsoft certified SBCs and Direct Routing to connect contact center solutions to Teams phone system infrastructure, enabling enhanced routing, configuration, and system insights.</span></span>

<span data-ttu-id="2c800-109">Les agents peuvent configurer des assistants virtuels automatisés et des files d’attente de routage basées sur les compétences pour recueillir des informations et connecter les clients avec des experts techniques.</span><span class="sxs-lookup"><span data-stu-id="2c800-109">Agents can set up automated virtual assistants and skill-based routing queues to gather information and connect customers with subject matter experts.</span></span>

<span data-ttu-id="2c800-110">**Principales caractéristiques de la fonctionnalité :**</span><span class="sxs-lookup"><span data-stu-id="2c800-110">**Feature highlights:**</span></span>

<span data-ttu-id="2c800-111">Bien que ces fonctionnalités ne sont pas une liste exhaustive des fonctionnalités de ce modèle d’intégration, les domaines clés sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="2c800-111">While these features aren't a comprehensive list of feature capabilities for this model of integration, the focus areas include:</span></span>

  - <span data-ttu-id="2c800-112">AuthN Office 365 pour que les agents se connectent à leur client Microsoft à partir de leur client CCaaS intégré</span><span class="sxs-lookup"><span data-stu-id="2c800-112">Office 365 authN for agents to connect to their Microsoft tenant from their integrated CCaaS client</span></span> 

  - <span data-ttu-id="2c800-113">Voir si des agents sont disponibles avec Teams</span><span class="sxs-lookup"><span data-stu-id="2c800-113">See when agents are available with Teams</span></span>

  - <span data-ttu-id="2c800-114">Transferts et appel de groupe avec Teams</span><span class="sxs-lookup"><span data-stu-id="2c800-114">Transfers and group call support with Teams</span></span> 

  - <span data-ttu-id="2c800-115">API Teams Graph et API de communication cloud pour l’intégration avec Teams</span><span class="sxs-lookup"><span data-stu-id="2c800-115">Teams Graph APIs and Cloud Communication APIs for integration with Teams</span></span> 

  - <span data-ttu-id="2c800-116">Ligne SIP multi-client pour prendre en charge plusieurs clients sur le SBC du fournisseur de solutions.</span><span class="sxs-lookup"><span data-stu-id="2c800-116">Multi-tenant SIP trunking to support several customers on solution provider’s SBC.</span></span>  

  - <span data-ttu-id="2c800-117">Fournisseurs de solutions pour utiliser le contrôleur de bordure de session certifié [ <span class="underline">Microsoft (SBC)</span>](../direct-routing-border-controllers.md)</span><span class="sxs-lookup"><span data-stu-id="2c800-117">Solution providers to use [<span class="underline">Microsoft certified session border controller (SBC)</span>](../direct-routing-border-controllers.md)</span></span>


### <a name="the-extend-model"></a>[<span data-ttu-id="2c800-118">**Modèle Étendre**</span><span class="sxs-lookup"><span data-stu-id="2c800-118">**The Extend model**</span></span>](#tab/extend)

<span data-ttu-id="2c800-119">Le modèle Étendre est intégré au client Teams à l’aide de la plateforme [du client Teams,](/microsoftteams/platform/overview)des [API Teams Graph](/graph/api/resources/teams-api-overview?view=graph-rest-1.0) et de l’API de communications cloud dans Microsoft [Graph.](/graph/api/resources/communications-api-overview?view=graph-rest-1.0)</span><span class="sxs-lookup"><span data-stu-id="2c800-119">The Extend model integrates with the Teams client using the [Teams client platform](/microsoftteams/platform/overview), [Teams Graph APIs](/graph/api/resources/teams-api-overview?view=graph-rest-1.0) and [Cloud Communications API in Microsoft Graph](/graph/api/resources/communications-api-overview?view=graph-rest-1.0).</span></span> <span data-ttu-id="2c800-120">Le modèle Étendre utilise également le système téléphonique de Teams pour tous les appels au centre de contacts et les expériences de contrôle d’appel, et le fournisseur de solutions du centre de contacts agit en tant qu’opérateur téléphonique en parallèle avec Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2c800-120">The Extend model also uses the Teams phone system for all contact center calls and call control experiences, and the contact center solution provider acts as a telephony carrier alongside Microsoft 365.</span></span>

<span data-ttu-id="2c800-121">Les agents peuvent utiliser Teams pour la collaboration interne et la communication externe, et peuvent tirer avantage de notes dynamiques et contextuelles en rapport avec les données de plusieurs systèmes avant de commencer un engagement, et ainsi éviter un changement de contexte coûteux.</span><span class="sxs-lookup"><span data-stu-id="2c800-121">Agents can use Teams for internal collaboration and external communication and can benefit from dynamic, contextual notes correlating data from multiple systems prior to starting an engagement and then avoid costly context switching.</span></span>

<span data-ttu-id="2c800-122">Les organisations peuvent concevoir des flux de travail et des configurations de routage avancées jusqu’à la personne et mesurer la qualité de leur système et de leurs interactions.</span><span class="sxs-lookup"><span data-stu-id="2c800-122">Organizations can design workflows and advanced routing configurations down to the individual and measure the quality of their system and interactions.</span></span>

<span data-ttu-id="2c800-123">**Principales caractéristiques de la fonctionnalité :**</span><span class="sxs-lookup"><span data-stu-id="2c800-123">**Feature highlights:**</span></span>

<span data-ttu-id="2c800-124">Bien que ces fonctionnalités ne sont pas une liste exhaustive des fonctionnalités de ce modèle d’intégration, les domaines clés sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="2c800-124">While these features aren't a comprehensive list of feature capabilities for this model of integration, the focus areas include:</span></span>

  - <span data-ttu-id="2c800-125">API Teams Graph et API de communication cloud pour l’intégration avec Teams</span><span class="sxs-lookup"><span data-stu-id="2c800-125">Teams Graph APIs and Cloud Communication APIs for integration with Teams</span></span> 

  - <span data-ttu-id="2c800-126">Application Teams pour les expériences de l’agent</span><span class="sxs-lookup"><span data-stu-id="2c800-126">Teams-based app for agent experiences</span></span> 

  - <span data-ttu-id="2c800-127">Teams comme point de terminaison d’appel principal pour les agents</span><span class="sxs-lookup"><span data-stu-id="2c800-127">Teams as the primary calling endpoint for the agents</span></span> 

  - <span data-ttu-id="2c800-128">Appel du client Teams pour tous les contrôles d’appel</span><span class="sxs-lookup"><span data-stu-id="2c800-128">Teams client calling for all the call controls</span></span>

  - <span data-ttu-id="2c800-129">Application d’expérience de l’agent pour teams web et client mobile</span><span class="sxs-lookup"><span data-stu-id="2c800-129">Agent experience app for both Teams web and mobile client</span></span>

  - <span data-ttu-id="2c800-130">Analyse, gestion des flux de travail, expériences basées sur les rôles pour les agents dans l’application CCaaS dans Teams</span><span class="sxs-lookup"><span data-stu-id="2c800-130">Analytics, workflow management, role-based experiences for agents in the CCaaS app in Teams</span></span>

  - <span data-ttu-id="2c800-131">Les expériences de conversation et de collaboration intégrées avec les clients Teams</span><span class="sxs-lookup"><span data-stu-id="2c800-131">Chat and collaboration experiences integrated with Teams clients</span></span> 

  - <span data-ttu-id="2c800-132">Préserver les performances et la qualité des expériences clientes teams dans toutes les applications</span><span class="sxs-lookup"><span data-stu-id="2c800-132">Preserve performance and quality of Teams client experiences in all apps</span></span>  

### <a name="the-power-model"></a>[<span data-ttu-id="2c800-133">**Modèle de puissance**</span><span class="sxs-lookup"><span data-stu-id="2c800-133">**The Power model**</span></span>](#tab/power)

<span data-ttu-id="2c800-134">Le modèle Power permet aux fournisseurs de solutions de créer des applications vocales azure natives à l’aide de l’infrastructure d’appels Teams et de la plateforme cliente pour offrir des solutions modernes et intelligentes pour une connexion collaborative entre les clients et les agents.</span><span class="sxs-lookup"><span data-stu-id="2c800-134">The Power model enables solution providers to create native Azure-based voice applications using the Teams calling infrastructure and client platform to deliver modern, intelligent solutions for collaborative customer and agent connection.</span></span> <span data-ttu-id="2c800-135">L’objectif du modèle Power est de fournir une expérience de centre de contacts à écran unique.</span><span class="sxs-lookup"><span data-stu-id="2c800-135">The goal of the Power model is to provide a one-app, one-screen contact center experience.</span></span>

<span data-ttu-id="2c800-136">**Principales caractéristiques de la fonctionnalité :**</span><span class="sxs-lookup"><span data-stu-id="2c800-136">**Feature highlights:**</span></span>

<span data-ttu-id="2c800-137">Bien que ces fonctionnalités ne sont pas une liste exhaustive des fonctionnalités de ce modèle d’intégration, les domaines clés sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="2c800-137">While these features aren't a comprehensive list of feature capabilities for this model of integration, the focus areas include:</span></span>

  - <span data-ttu-id="2c800-138">Expériences formelles de l’agent activées en natif pour la communication sur tout canal via le SDK Teams</span><span class="sxs-lookup"><span data-stu-id="2c800-138">Formal agent experiences natively enabled for omni-channel communication via Teams SDK</span></span> 

  - <span data-ttu-id="2c800-139">Utiliser les services de collaboration dans Teams pour la collaboration avec les agents et les interactions avec les clients</span><span class="sxs-lookup"><span data-stu-id="2c800-139">Use Teams collaboration services for agent collaboration and customer interactions</span></span>  

  - <span data-ttu-id="2c800-140">Approvisionnement rapide des services cloud, déploiement en tout lieu</span><span class="sxs-lookup"><span data-stu-id="2c800-140">Rapid provisioning of cloud services, deploy anywhere</span></span> 

  - <span data-ttu-id="2c800-141">Direct conversation control and interaction with users during Teams conversations</span><span class="sxs-lookup"><span data-stu-id="2c800-141">Direct conversation control and interaction with users during Teams conversations</span></span> 

>[!NOTE]
> <span data-ttu-id="2c800-142">Le modèle power sera disponible vers la fin de l’année 2021.</span><span class="sxs-lookup"><span data-stu-id="2c800-142">The Power model will be available towards the end of 2021.</span></span>
