---
title: "Présentation de Microsoft Teams | Support Microsoft"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Découvrez Microsoft teams, son infrastructure et son utilisation avec Office 365."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 7f28dc24baab9ba3d61b3181c05a09d108c320f3
ms.sourcegitcommit: e0efee5350da54a1f1ae1c317f8613652c820bc6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/25/2017
---
<a name="overview-of-microsoft-teams"></a><span data-ttu-id="773c2-103">Présentation de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="773c2-103">Overview of Microsoft Teams</span></span>
===========================
|  |  |
|---------|---------|
|<iframe width="560" height="315" src="https://www.youtube.com/embed/FFQszYALS_A" frameborder="0" allowfullscreen></iframe> | |

<span data-ttu-id="773c2-p101">Microsoft Teams rassemble toutes les fonctionnalités d'Office 365, pour fournir une véritable plateforme dédiée à la communication et favoriser le travail en équipe et donner aux clients la possibilité de créer un environnement plus ouvert, fluide et numérique. Microsoft Teams est basé sur des technologies Microsoft existantes interreliées par d'autres groupes Office 365.</span><span class="sxs-lookup"><span data-stu-id="773c2-p101">Microsoft Teams brings together the full breadth and depth of Office 365, to provide a true chat-based hub for teamwork and give customers the opportunity to create a more open, fluid, and digital environment. Microsoft Teams is built on existing Microsoft technologies woven together by Office 365 Groups.</span></span> 

<span data-ttu-id="773c2-106">Prêt à l'emploi, Microsoft Teams utilise les identités stockées dans Azure Active Directory (Azure AD) et s'intègre aux autres services dans Office 365, pour créer un site SharePoint Online et une boîte aux lettre de groupe Exchange Online pour chaque équipe créée.</span><span class="sxs-lookup"><span data-stu-id="773c2-106">Out of the box, Microsoft Teams leverages identities stored in Azure Active Directory (Azure AD) and integrates with the other services within Office 365, to create a SharePoint online site and an Exchange Online group mailbox for each team created.</span></span>

<span data-ttu-id="773c2-107">La fonctionnalité de conversation permanente de Teams est fournie par un service de communication qui interagit avec le substrat Office 365, faisant apparaître de nombreuses fonctionnalités Office 365 intégrées, telles que l'archivage et eDiscovery pour les données échangées dans Teams.</span><span class="sxs-lookup"><span data-stu-id="773c2-107">Microsoft Teams persistent chat capability is provided by a chat service that interacts with the Office 365 substrate, surfacing many of the built-in Office 365 capabilities, such as archiving and eDiscovery to the data being exchanged in Microsoft Teams.</span></span>

<span data-ttu-id="773c2-108">L'expérience d'appels et de réunions Microsoft Teams est basée sur l'infrastructure cloud de nouvelle génération, également utilisée par Skype et Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="773c2-108">Microsoft Teams also provides a calling and meetings experience that is built on the next generation cloud-based infrastructure that is also used by Skype and Skype for Business. These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry, and quality diagnostics.</span></span> <span data-ttu-id="773c2-109">Ces investissements technologiques incluent les services cloud Azure pour le traitement multimédia et la signalisation, le codec vidéo H.264, le codec audio SILK et Opus, la résilience réseau, la télémétrie et le diagnostic de qualité.</span><span class="sxs-lookup"><span data-stu-id="773c2-109">Microsoft Teams also provides a calling and meetings experience that is built on the next generation cloud-based infrastructure that is also used by Skype and Skype for Business. These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry, and quality diagnostics.</span></span>

<span data-ttu-id="773c2-110">Pour étendre les fonctionnalités de Teams, utilisez des connecteurs, onglets et bots disponibles en tant qu'[applications](https://go.microsoft.com/fwlink/?linkid=854629) pour introduire les interactions avec des informations externes, du contenu et des bots intelligents dans Teams.</span><span class="sxs-lookup"><span data-stu-id="773c2-110">To extend Microsoft Teams capabilities, Connectors, Tabs, and Bots are available as [Apps](https://go.microsoft.com/fwlink/?linkid=854629) to bring external information, content, and intelligent bots’ interactions to Microsoft Teams.</span></span>

<a name="microsoft-teams-infrastructure"></a><span data-ttu-id="773c2-111">Infrastructure de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="773c2-111">Microsoft Teams infrastructure</span></span>
------------------------------

<span data-ttu-id="773c2-112">Teams est basé sur des technologies Microsoft existantes interreliées par d'autres groupes Office 365.</span><span class="sxs-lookup"><span data-stu-id="773c2-112">Teams is built on existing Microsoft technologies, woven together by Office 365 Groups.</span></span> <span data-ttu-id="773c2-113">Avec le cloud de Microsoft, les organisations peuvent profiter de performances excellentes et d'une grande fiabilité lors de l'utilisation de Teams dans le cadre de leur scénario de collaboration.</span><span class="sxs-lookup"><span data-stu-id="773c2-113">Microsoft Teams is built on existing Microsoft technologies woven together by Office 365 Groups. Powered by Microsoft’s cloud, organizations can expect excellent performance and reliability when leveraging Microsoft Teams as part of their collaboration story.</span></span>

<span data-ttu-id="773c2-114">Prête à l'emploi, une équipe créée dans Teams formera un groupe Office 365 avec un site SharePoint Online associé ainsi qu'une bibliothèque de documents, une boîte aux lettres Exchange Online qui sera utilisé par Teams pour stocker des informations, telles que des invitations à des réunions.</span><span class="sxs-lookup"><span data-stu-id="773c2-114">Out of the box, a team created in Teams will create an Office 365 Group, a SharePoint Online site (complete with a document library), and an Exchange Online group mailbox, which will be used by Teams to store information such as meeting invites.</span></span> <span data-ttu-id="773c2-115">Une équipe peut être créée à l'aide de groupes Office 365 existants, ce qui permet de transférer les adhésions de groupe, le contenu stocké dans SharePoint Online et dans Exchange Online vers Teams.</span><span class="sxs-lookup"><span data-stu-id="773c2-115">A team can be created using existing Office 365 Groups, allowing existing group memberships, and contents stored in SharePoint Online and Exchange Online to be ported to Teams.</span></span>

<span data-ttu-id="773c2-116">La fonctionnalité de conversation permanente de Teams est fournie par un service de communication qui interagit avec Office 365, faisant apparaître de nombreuses fonctionnalités Office 365 intégrées, telles que l'archivage et eDiscovery pour les données échangées dans Teams.</span><span class="sxs-lookup"><span data-stu-id="773c2-116">Microsoft Teams persistent chat capability is provided by a chat service that interacts with the Office 365 substrate, surfacing many of the built-in Office 365 capabilities, such as archiving and eDiscovery to the data being exchanged in Microsoft Teams.</span></span>

<span data-ttu-id="773c2-117">Pour compléter la fonctionnalité Teams comme outil de conversation permanente, qui permet de mener des conversations informelles en temps réel, Teams fournit également une expérience d'appels et de réunions basée sur l'infrastructure cloud de nouvelle génération, également utilisée par Skype et Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="773c2-117">To complement Microsoft Teams capability as a persistent chat board where informal, real-time, conversations around very focused topics or specific sub-groups within the group take place, Teams also provides a meeting’s experience built on the next generation cloud-based infrastructure that is also used by Skype and Skype for Business. These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry, and quality diagnostics.</span></span> <span data-ttu-id="773c2-118">Ces investissements technologiques incluent les services cloud Azure pour le traitement multimédia et la signalisation, le codec vidéo H.264, le codec audio SILK et Opus, la résilience réseau, la télémétrie et le diagnostic de qualité.</span><span class="sxs-lookup"><span data-stu-id="773c2-118">Microsoft Teams also provides a calling and meetings experience that is built on the next generation cloud-based infrastructure that is also used by Skype and Skype for Business. These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry, and quality diagnostics.</span></span>

<span data-ttu-id="773c2-119">Les groupes Office 365 utilisent les identités stockées dans Azure Active Directory (Azure AD) et en tant que tel, toutes les fonctionnalités d'authentification et d'autorisation dans Azure AD, comme la prise en charge de l’authentification multifacteur, sont déjà disponibles dans Teams.</span><span class="sxs-lookup"><span data-stu-id="773c2-119">Office 365 Groups leverage identities stored in Azure Active Directory (Azure AD) and as such, all authentication and authorization capabilities in Azure AD, such as support for multi-factor authentication (MFA), is readily available for use by Microsoft Teams.</span></span>


<a name="microsoft-teams-and-office-365"></a><span data-ttu-id="773c2-120">Microsoft Teams et Office 365</span><span class="sxs-lookup"><span data-stu-id="773c2-120">Microsoft Teams and Office 365</span></span>
------------------------------

<span data-ttu-id="773c2-121">Les besoins des groupes divergent en fonction de leur rôle et de leur mode de travail.</span><span class="sxs-lookup"><span data-stu-id="773c2-121">Different groups have various needs, based on their functional role and workstyle.</span></span> <span data-ttu-id="773c2-122">Office 365 est conçu pour s'adapter au mode de travail unique de chaque groupe et inclut, entre autres, les applications dédiées et intégrées suivantes :</span><span class="sxs-lookup"><span data-stu-id="773c2-122">Different groups have various needs based on their functional role and workstyle. Office 365 is designed for the unique workstyle of every group and includes purpose-built, integrated applications, such as:</span></span>

-   <span data-ttu-id="773c2-123">Outlook pour la messagerie d'entreprise, désormais inclus avec la fonctionnalité de groupe</span><span class="sxs-lookup"><span data-stu-id="773c2-123">Outlook for enterprise-grade email, now with groups functionality.</span></span>

-   <span data-ttu-id="773c2-124">SharePoint pour les sites et portails, des services de contenu intelligents, l'automatisation de processus métiers et la recherche dans l'entreprise</span><span class="sxs-lookup"><span data-stu-id="773c2-124">SharePoint for sites and portals, intelligent content services, business process automation and enterprise search.</span></span>

-   <span data-ttu-id="773c2-125">Yammer pour les connexions à l'échelle de l'entreprise</span><span class="sxs-lookup"><span data-stu-id="773c2-125">Yammer for driving company-wide connections</span></span>

-   <span data-ttu-id="773c2-126">Skype Entreprise comme dorsale pour les fonctions audio et vidéo de l'entreprise</span><span class="sxs-lookup"><span data-stu-id="773c2-126">Skype for Business as the backbone for enterprise voice and video.</span></span>

-   <span data-ttu-id="773c2-127">Et à présent, Microsoft Teams, le nouvel espace de travail dédié à la communication dans Office 365</span><span class="sxs-lookup"><span data-stu-id="773c2-127">And now, Microsoft Teams, the new chat-based workspace in Office 365.</span></span>

<span data-ttu-id="773c2-p107">Voici quelques scénarios d'utilisation courants pour chaque application dans Office 365. Pour obtenir des instructions détaillées, rendez-vous dans la [Bibliothèque de productivité FastTrack](https://go.microsoft.com/fwlink/?linkid=854630).</span><span class="sxs-lookup"><span data-stu-id="773c2-p107">Here are common use cases for each application in Office 365. For detailed usage guidance, visit the [FastTrack Productivity Library](https://go.microsoft.com/fwlink/?linkid=854630).</span></span>

![](media/Overview_of_Microsoft_Teams_image1.png)

-   <span data-ttu-id="773c2-130">Utilisée par les utilisateurs et les équipes pour collaborer en temps réel dans le même groupe de membres</span><span class="sxs-lookup"><span data-stu-id="773c2-130">Leveraged by users and teams who are looking to collaborate in real-time with the same group of people.</span></span>

-   <span data-ttu-id="773c2-131">Aide les équipes qui souhaitent retravailler rapidement sur un projet tout en partageant des fichiers et en collaborant sur des livrables partagés</span><span class="sxs-lookup"><span data-stu-id="773c2-131">Helps teams looking to iterate quickly on a project while sharing files and collaborating on shared deliverables.</span></span>

-   <span data-ttu-id="773c2-132">Permet aux utilisateur de se connecter à une large gamme d'outils dans leur espace de travail (Planificateur, Power BI, GitHub, etc.)</span><span class="sxs-lookup"><span data-stu-id="773c2-132">Allows Users looking to connect a wide range of tools into their workspace (such as Planner, Power BI, GitHub, etc.).</span></span>

![](media/Overview_of_Microsoft_Teams_image2.png)

-   <span data-ttu-id="773c2-133">Pour les utilisateurs qui préfèrent collaborer dans l'environnement de messagerie familier et/ou de manière plus formelle et structurée</span><span class="sxs-lookup"><span data-stu-id="773c2-133">Leveraged by users who prefer to collaborate in the familiar environment of email and/or a more formal, structured manner.</span></span>

-   <span data-ttu-id="773c2-134">Fournit des processus métiers spécifiques qui requièrent l'utilisation de la messagerie pour transmettre des documents et des'informations à l'extérieur comme à l'intérieur de l'entreprise</span><span class="sxs-lookup"><span data-stu-id="773c2-134">Provides specific business processes that require email usage to transmit documents and information inside and outside corporate boundaries.</span></span>

-   <span data-ttu-id="773c2-135">Contacte les utilisateurs hors des organisations ou groupes de travail immédiats</span><span class="sxs-lookup"><span data-stu-id="773c2-135">Communicates and connects with users who are outside of immediate workgroups or organizations.</span></span>

![](media/Overview_of_Microsoft_Teams_image3.png)

-   <span data-ttu-id="773c2-136">Permet de connecter les utilisateurs dans l'organisation pour former des communautés spécialisées et partager des meilleures pratiques</span><span class="sxs-lookup"><span data-stu-id="773c2-136">Leveraged to help connect users across the organization to organize around communities of practice and share best practices.</span></span>

-   <span data-ttu-id="773c2-137">Améliore les flux de travail inter-fonctionnels via une plateforme de flux ouverte et transparente</span><span class="sxs-lookup"><span data-stu-id="773c2-137">Improves cross-functional workflows through an open and transparent feed-based platform</span></span>

-   <span data-ttu-id="773c2-138">Favorise l'implication des dirigeants dans les conversations bidirectionnelles entre la direction et les employés</span><span class="sxs-lookup"><span data-stu-id="773c2-138">Fosters executive-employee engagement with two-way conversations between leadership and the wider employee base</span></span>

-   <span data-ttu-id="773c2-139">Encourage vos intervenants de première ligne à partager et recevoir des connaissances et compétences</span><span class="sxs-lookup"><span data-stu-id="773c2-139">Ignites your frontline workforce to share and receive knowledge and expertise</span></span>

![](media/Overview_of_Microsoft_Teams_image4.png)

-   <span data-ttu-id="773c2-140">Utilisée pour la communication et la collaboration internes et externes en temps réel avec les clients/partenaires</span><span class="sxs-lookup"><span data-stu-id="773c2-140">Leveraged for real-time communication and collaboration both internally and externally with customers/partners.</span></span>

-   <span data-ttu-id="773c2-141">Fournit des fonctionnalités audio, vidéo et de partage de contenu pour les réunions de grandes ou petites équipes (y compris des conférences comprenant jusqu'à 10 000 participants)</span><span class="sxs-lookup"><span data-stu-id="773c2-141">Provides meetings with audio, video and content with small or large teams (including Town Halls with up to 10,000 participants).</span></span>

-   <span data-ttu-id="773c2-142">Fournit la fonctionnalité téléphonique d'entreprise</span><span class="sxs-lookup"><span data-stu-id="773c2-142">Offers enterprise telephony functionality.</span></span>


![](media/Overview_of_Microsoft_Teams_image5.png)

-   <span data-ttu-id="773c2-143">Utilisée pour les sites et portails (par ex., actualité de l'entreprise, recherche et documentation de collaboration)</span><span class="sxs-lookup"><span data-stu-id="773c2-143">Leveraged for sites and portals (e.g. company news & announcements, search, and document collaboration).</span></span>

-   <span data-ttu-id="773c2-144">Implémente l'automatisation des processus métiers dans des bibliothèques de documents et listes d'informations en intégrant Microsoft Flow et PowerApps</span><span class="sxs-lookup"><span data-stu-id="773c2-144">Implements business process automation on document libraries and lists of information by integrating Microsoft Flow and PowerApps.</span></span>

-   <span data-ttu-id="773c2-145">Site d'équipe SharePoint puissant automatiquement fourni pour chaque équipe Microsoft Teams pour le stockage de fichiers, l'actualité de l'équipe, les pages, les listes, et plus encore.</span><span class="sxs-lookup"><span data-stu-id="773c2-145">Full-powered SharePoint team site automatically provisioned for every Microsoft Team for file storage, team news, pages, lists and more.</span></span>

-   <span data-ttu-id="773c2-146">Consultez [Interaction de SharePoint Online et OneDrive Entreprise avec Microsoft Teams](SharePoint-OneDrive-interact.md)</span><span class="sxs-lookup"><span data-stu-id="773c2-146">See [How SharePoint Online and OneDrive for Business interact with Teams](SharePoint-OneDrive-interact.md)</span></span>
