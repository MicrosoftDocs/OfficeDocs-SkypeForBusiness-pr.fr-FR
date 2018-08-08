---
title: Présentation de Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: ''
description: Découvrez Microsoft teams, son infrastructure et son utilisation avec Office 365.
localization_priority: Priority
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 86698a3bb7535a20b7fb1b6833062d118f2f9eae
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20967128"
---
<a name="overview-of-microsoft-teams"></a><span data-ttu-id="21185-103">Présentation de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="21185-103">Overview of Microsoft Teams</span></span>
===========================

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=ccf507a4-4ec4-4d61-9fb0-c86b5f1fc2a6&AutoPlayVideo=false] 


<span data-ttu-id="21185-p101">Microsoft Teams rassemble toutes les fonctionnalités d'Office 365, pour fournir une véritable plateforme dédiée à la communication et favoriser le travail en équipe et donner aux clients la possibilité de créer un environnement plus ouvert, fluide et numérique. Microsoft Teams est basé sur des technologies Microsoft existantes interreliées par d'autres groupes Office 365.</span><span class="sxs-lookup"><span data-stu-id="21185-p101">Microsoft Teams brings together the full breadth and depth of Office 365, to provide a true chat-based hub for teamwork and give customers the opportunity to create a more open, fluid, and digital environment. Microsoft Teams is built on existing Microsoft technologies woven together by Office 365 Groups.</span></span> 

<span data-ttu-id="21185-106">Prêt à l'emploi, Microsoft Teams utilise les identités stockées dans Azure Active Directory (Azure AD) et s'intègre aux autres services dans Office 365, pour créer un site SharePoint Online et une boîte aux lettre de groupe Exchange Online pour chaque équipe créée.</span><span class="sxs-lookup"><span data-stu-id="21185-106">Out of the box, Teams leverages identities stored in Azure Active Directory (Azure AD) and integrates with the other services within Office 365, to create a SharePoint online site and an Exchange Online group mailbox for each team created.</span></span>

<span data-ttu-id="21185-107">Toute personne possédant un compte de messagerie consommateur ou de l’entreprise, comme Outlook, Gmail ou d’autres personnes, peut participer à en tant qu’invité dans les équipes.</span><span class="sxs-lookup"><span data-stu-id="21185-107">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams.</span></span> <span data-ttu-id="21185-108">Tous les invités dans les équipes sont couverts par la même conformité et audit protection en tant que le reste d’Office 365 et les invités peuvent être gérées de manière sécurisée dans Azure AD.</span><span class="sxs-lookup"><span data-stu-id="21185-108">All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and guests can be managed securely within Azure AD.</span></span> <span data-ttu-id="21185-109">Administrateurs peuvent centraliser gérer comment participer à des invités dans leur environnement Office 365 et facilement afficher, ajouter ou révoquer l’accès au client d’hôte d’un invité.</span><span class="sxs-lookup"><span data-stu-id="21185-109">Admins can centrally manage how guests participate within their Office 365 environment and easily view, add, or revoke a guest’s access to the host tenant.</span></span>

<span data-ttu-id="21185-110">Teams fournit une fonctionnalité de conversation permanente, d’appels et réunions et permet d’accéder facilement aux autres composants d’Office 365, et offre également des possibilités d’extension.</span><span class="sxs-lookup"><span data-stu-id="21185-110">Teams provides a persistent chat capability, calling and meetings, easy access to other components of Office 365 as well as a robust extensibility story.</span></span>  <span data-ttu-id="21185-111">Vous disposez ainsi d'une plateforme dédiée au travail en équipe qui est appropriée pour les grandes entreprises, les petites organisations et les entreprises de taille intermédiaire.</span><span class="sxs-lookup"><span data-stu-id="21185-111">This provides a hub for teamwork that is appropriate for enterprise companies, small organizations and everyone in between.</span></span>  

<span data-ttu-id="21185-112">Pour étendre les fonctionnalités de Teams, utilisez des connecteurs, onglets et bots disponibles en tant qu'[applications](https://go.microsoft.com/fwlink/?linkid=854629) pour introduire les interactions avec des informations externes, du contenu et des bots intelligents dans Teams.</span><span class="sxs-lookup"><span data-stu-id="21185-112">To extend Teams capabilities, use Connectors, Tabs, and Bots - available as [Apps](https://go.microsoft.com/fwlink/?linkid=854629), to bring external information, content, and intelligent bot interactions to Teams.</span></span>  

<a name="microsoft-teams-infrastructure"></a><span data-ttu-id="21185-113">Infrastructure de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="21185-113">Microsoft Teams infrastructure</span></span>
------------------------------

<span data-ttu-id="21185-114">Teams est basé sur des technologies Microsoft existantes interreliées par d'autres groupes Office 365.</span><span class="sxs-lookup"><span data-stu-id="21185-114">Teams is built on existing Microsoft technologies, woven together by Office 365 Groups.</span></span> <span data-ttu-id="21185-115">Avec le cloud de Microsoft, les organisations peuvent profiter de performances excellentes et d'une grande fiabilité lors de l'utilisation de Teams dans le cadre de leur scénario de collaboration.</span><span class="sxs-lookup"><span data-stu-id="21185-115">Powered by the Microsoft cloud, organizations can expect excellent performance and reliability when leveraging Teams as part of their collaboration story.</span></span>

<span data-ttu-id="21185-116">Prête à l'emploi, une équipe créée dans Teams formera un groupe Office 365 avec un site SharePoint Online associé ainsi qu'une bibliothèque de documents, une boîte aux lettres Exchange Online qui sera utilisé par Teams pour stocker des informations, telles que des invitations à des réunions.</span><span class="sxs-lookup"><span data-stu-id="21185-116">Out of the box, a team created in Teams will create an Office 365 Group, a SharePoint Online site (complete with a document library), and an Exchange Online group mailbox, which will be used by Teams to store information such as meeting invites.</span></span> <span data-ttu-id="21185-117">Une équipe peut être créée à l'aide de groupes Office 365 existants, ce qui permet de transférer les adhésions de groupe, le contenu stocké dans SharePoint Online et dans Exchange Online vers Teams.</span><span class="sxs-lookup"><span data-stu-id="21185-117">A team can be created using existing Office 365 Groups, allowing existing group memberships, and contents stored in SharePoint Online and Exchange Online to be ported to Teams.</span></span>

<span data-ttu-id="21185-118">Pour compléter la capacité des équipes comme un forum de conversation permanente où des conversations en temps réel informelles ont lieu, les équipes également fournit un appel et expérience reposant sur le prochaine génération basée sur le cloud infrastructure qui est également utilisé par Skype et Skype pour la réunion Business.</span><span class="sxs-lookup"><span data-stu-id="21185-118">To complement the Teams capability as a persistent chat board where informal, real-time conversations take place, Teams also provides a calling and meeting experience built on the next generation cloud-based infrastructure that is also used by Skype and Skype for Business.</span></span> <span data-ttu-id="21185-119">Ces investissements technologiques incluent les services cloud Azure pour le traitement multimédia et la signalisation, le codec vidéo H.264, le codec audio SILK et Opus, la résilience réseau, la télémétrie et le diagnostic de qualité.</span><span class="sxs-lookup"><span data-stu-id="21185-119">These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry, and quality diagnostics.</span></span>

<span data-ttu-id="21185-120">Les groupes Office 365 utilisent les identités stockées dans Azure Active Directory (Azure AD) et en tant que tel, toutes les fonctionnalités d'authentification et d'autorisation dans Azure AD, comme la prise en charge de l’authentification multifacteur, sont déjà disponibles dans Teams.</span><span class="sxs-lookup"><span data-stu-id="21185-120">Office 365 Groups leverage identities stored in Azure Active Directory (Azure AD) and as such, all authentication and authorization capabilities in Azure AD, such as support for multi-factor authentication (MFA), are readily available for use by Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="21185-121">En fonction des commentaires des clients, les nouveaux groupes de 365 Office générés suite à la création d’une équipe dans Microsoft Teams n’apparaît plus dans Outlook par défaut.</span><span class="sxs-lookup"><span data-stu-id="21185-121">Based on customer feedback, new Office 365 Groups generated as a result of creating a team in Microsoft Teams will no longer show in Outlook by default.</span></span> <span data-ttu-id="21185-122">Pour les clients qui vous souhaitez continuer avec le comportement de l’affichage de ces groupes dans Outlook existant, une applet de commande Exchange Online PowerShell est fournie qui permettent le groupe pour l’expérience Outlook.</span><span class="sxs-lookup"><span data-stu-id="21185-122">For customers that want to continue with the existing behavior of showing these groups in Outlook, an Exchange Online PowerShell cmdlet will be provided which can enable the group for the Outlook experience.</span></span> <span data-ttu-id="21185-123">Groupes créés via Outlook et activé plus tard pour les équipes continuera à afficher dans Outlook et les équipes.</span><span class="sxs-lookup"><span data-stu-id="21185-123">Groups created through Outlook and then later enabled for Teams will continue to show in both Outlook and Teams.</span></span> <span data-ttu-id="21185-124">Cette mise à jour sera progressivement roll out entre Outlook et les équipes dans les mois à venir.</span><span class="sxs-lookup"><span data-stu-id="21185-124">This update will gradually roll out across Outlook and Teams in the coming months.</span></span>


<a name="microsoft-teams-and-office-365"></a><span data-ttu-id="21185-125">Microsoft Teams et Office 365</span><span class="sxs-lookup"><span data-stu-id="21185-125">Microsoft Teams and Office 365</span></span>
------------------------------

<span data-ttu-id="21185-126">Les besoins des groupes divergent en fonction de leur rôle et de leur mode de travail.</span><span class="sxs-lookup"><span data-stu-id="21185-126">Different groups have various needs, based on their functional role and workstyle.</span></span> <span data-ttu-id="21185-127">Office 365 est conçu pour s'adapter au mode de travail unique de chaque groupe et inclut, entre autres, les applications dédiées et intégrées suivantes :</span><span class="sxs-lookup"><span data-stu-id="21185-127">Office 365 is designed for the unique workstyle of every group and includes purpose-built, integrated applications, including:</span></span>

-   <span data-ttu-id="21185-128">Outlook pour la messagerie d'entreprise, désormais inclus avec la fonctionnalité de groupe</span><span class="sxs-lookup"><span data-stu-id="21185-128">Outlook for enterprise-grade email, now with groups functionality</span></span>

-   <span data-ttu-id="21185-129">SharePoint pour les sites et portails, des services de contenu intelligents, l'automatisation de processus métiers et la recherche dans l'entreprise</span><span class="sxs-lookup"><span data-stu-id="21185-129">SharePoint for sites and portals, intelligent content services, business process automation and enterprise search</span></span>

-   <span data-ttu-id="21185-130">Yammer pour les connexions à l'échelle de l'entreprise</span><span class="sxs-lookup"><span data-stu-id="21185-130">Yammer for driving company-wide connections</span></span>

-   <span data-ttu-id="21185-131">Skype Entreprise comme dorsale pour les fonctions audio et vidéo de l'entreprise</span><span class="sxs-lookup"><span data-stu-id="21185-131">Skype for Business as the backbone for enterprise voice and video</span></span>

-   <span data-ttu-id="21185-132">Et à présent, Microsoft Teams, le nouvel espace de travail dédié à la communication dans Office 365</span><span class="sxs-lookup"><span data-stu-id="21185-132">And now, Microsoft Teams, the new chat-based workspace in Office 365</span></span>

<span data-ttu-id="21185-p109">Voici quelques scénarios d'utilisation courants pour chaque application dans Office 365. Pour obtenir des instructions détaillées, rendez-vous dans la [Bibliothèque de productivité FastTrack](https://go.microsoft.com/fwlink/?linkid=854630).</span><span class="sxs-lookup"><span data-stu-id="21185-p109">Here are common use cases for each application in Office 365. For detailed usage guidance, visit the [FastTrack Productivity Library](https://go.microsoft.com/fwlink/?linkid=854630).</span></span>

![Icône Microsoft Teams.](media/Overview_of_Microsoft_Teams_image1.png)

-   <span data-ttu-id="21185-136">Utilisée par les utilisateurs et les équipes pour collaborer en temps réel dans le même groupe de membres</span><span class="sxs-lookup"><span data-stu-id="21185-136">Leveraged by users and teams who are looking to collaborate in real-time with the same group of people.</span></span>

-   <span data-ttu-id="21185-137">Aide les équipes qui souhaitent retravailler rapidement sur un projet tout en partageant des fichiers et en collaborant sur des livrables partagés</span><span class="sxs-lookup"><span data-stu-id="21185-137">Helps teams looking to iterate quickly on a project while sharing files and collaborating on shared deliverables.</span></span>

-   <span data-ttu-id="21185-138">Permet aux utilisateurs de se connecter une large gamme d’outils dans leur espace de travail (telles que le planificateur, Power BI, référentiels, etc.).</span><span class="sxs-lookup"><span data-stu-id="21185-138">Allows users to connect a wide range of tools into their workspace (such as Planner, Power BI, GitHub, etc.).</span></span>

![Icône Microsoft Outlook.](media/Overview_of_Microsoft_Teams_image2.png)

-   <span data-ttu-id="21185-140">Pour les utilisateurs qui préfèrent collaborer dans l'environnement de messagerie familier et/ou de manière plus formelle et structurée</span><span class="sxs-lookup"><span data-stu-id="21185-140">Leveraged by users who prefer to collaborate in the familiar environment of email and/or a more formal, structured manner.</span></span>

-   <span data-ttu-id="21185-141">Fournit des processus métiers spécifiques qui requièrent l'utilisation de la messagerie pour transmettre des documents et des'informations à l'extérieur comme à l'intérieur de l'entreprise</span><span class="sxs-lookup"><span data-stu-id="21185-141">Provides specific business processes that require email usage to transmit documents and information inside and outside corporate boundaries.</span></span>

-   <span data-ttu-id="21185-142">Contacte les utilisateurs hors des organisations ou groupes de travail immédiats</span><span class="sxs-lookup"><span data-stu-id="21185-142">Communicates and connects with users who are outside of immediate workgroups or organizations.</span></span>

![Icône Yammer.](media/Overview_of_Microsoft_Teams_image3.png)

-   <span data-ttu-id="21185-144">Permet de connecter les utilisateurs dans l'organisation pour former des communautés spécialisées et partager des meilleures pratiques</span><span class="sxs-lookup"><span data-stu-id="21185-144">Leveraged to help connect users across the organization to organize around communities of practice and share best practices.</span></span>

-   <span data-ttu-id="21185-145">Améliore les flux de travail inter-fonctionnels via une plateforme de flux ouverte et transparente</span><span class="sxs-lookup"><span data-stu-id="21185-145">Improves cross-functional workflows through an open and transparent feed-based platform</span></span>

-   <span data-ttu-id="21185-146">Favorise l'implication des dirigeants dans les conversations bidirectionnelles entre la direction et les employés</span><span class="sxs-lookup"><span data-stu-id="21185-146">Fosters executive-employee engagement with two-way conversations between leadership and the wider employee base</span></span>

-   <span data-ttu-id="21185-147">Encourage vos intervenants de première ligne à partager et recevoir des connaissances et compétences</span><span class="sxs-lookup"><span data-stu-id="21185-147">Ignites your frontline workforce to share and receive knowledge and expertise</span></span>

![Icône Skype Entreprise.](media/Overview_of_Microsoft_Teams_image4.png)

-   <span data-ttu-id="21185-149">Utilisée pour la communication et la collaboration internes et externes en temps réel avec les clients/partenaires</span><span class="sxs-lookup"><span data-stu-id="21185-149">Leveraged for real-time communication and collaboration both internally and externally with customers/partners.</span></span>

-   <span data-ttu-id="21185-150">Fournit des fonctionnalités audio, vidéo et de partage de contenu pour les réunions de grandes ou petites équipes (y compris des conférences comprenant jusqu'à 10 000 participants)</span><span class="sxs-lookup"><span data-stu-id="21185-150">Provides meetings with audio, video and content with small or large teams (including Town Halls with up to 10,000 participants).</span></span>

-   <span data-ttu-id="21185-151">Fournit la fonctionnalité téléphonique d'entreprise</span><span class="sxs-lookup"><span data-stu-id="21185-151">Offers enterprise telephony functionality.</span></span>


![Icône Microsoft SharePoint.](media/Overview_of_Microsoft_Teams_image5.png)

-   <span data-ttu-id="21185-153">Utilisée pour les sites et portails (par ex., actualité de l'entreprise, recherche et documentation de collaboration).</span><span class="sxs-lookup"><span data-stu-id="21185-153">Leveraged for sites and portals (e.g. company news & announcements, search, and document collaboration).</span></span>

-   <span data-ttu-id="21185-154">Implémente l'automatisation des processus métiers dans des bibliothèques de documents et listes d'informations en intégrant Microsoft Flow et PowerApps</span><span class="sxs-lookup"><span data-stu-id="21185-154">Implements business process automation on document libraries and lists of information by integrating Microsoft Flow and PowerApps.</span></span>

-   <span data-ttu-id="21185-155">Site d'équipe SharePoint puissant automatiquement fourni pour chaque équipe Microsoft Teams pour le stockage de fichiers, l'actualité de l'équipe, les pages, les listes, et plus encore.</span><span class="sxs-lookup"><span data-stu-id="21185-155">Full-powered SharePoint team site automatically provisioned for every Microsoft Team for file storage, team news, pages, lists and more.</span></span>

-   <span data-ttu-id="21185-156">Consultez [Interaction de SharePoint Online et OneDrive Entreprise avec Microsoft Teams](SharePoint-OneDrive-interact.md)</span><span class="sxs-lookup"><span data-stu-id="21185-156">See [How SharePoint Online and OneDrive for Business interact with Teams](SharePoint-OneDrive-interact.md)</span></span>

## <a name="teams-known-issuesknown-issuesmd"></a>[<span data-ttu-id="21185-157">Problèmes connus dans Teams</span><span class="sxs-lookup"><span data-stu-id="21185-157">Teams known issues</span></span>](Known-issues.md)

## <a name="teams-client-release-noteshttpssupportofficecomarticlerelease-notes-for-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de"></a>[<span data-ttu-id="21185-158">Notes de publication du client Teams</span><span class="sxs-lookup"><span data-stu-id="21185-158">Teams client release notes</span></span>](https://support.office.com/article/Release-notes-for-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)

## <a name="what-happened-to-the-teams-admin-faq"></a><span data-ttu-id="21185-159">Qu’est devenue la FAQ Microsoft Teams dédiée aux administrateurs ?</span><span class="sxs-lookup"><span data-stu-id="21185-159">What happened to the Teams admin FAQ?</span></span>

<span data-ttu-id="21185-160">Bien que cette FAQ dédiée aux administrateurs ait été d’une grande aide lors du lancement de Microsoft Teams, c’est rapidement devenu un véritable « fourre-tout ».</span><span class="sxs-lookup"><span data-stu-id="21185-160">While the Teams Admin FAQ was handy when we first released Teams, it quickly became a "junk drawer" that made it hard to find anything specific.</span></span> <span data-ttu-id="21185-161">Nous avons donc décidé d’y mettre fin pour incorporer les précieuses informations qu’elle renfermait dans la présente documentation de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="21185-161">So we busted apart the FAQ and incorporated its valuable information into the Teams documentation that you're looking at right now.</span></span> <span data-ttu-id="21185-162">Vous retrouverez donc l’intégralité du contenu de la FAQ dans ce document, mais en contexte.</span><span class="sxs-lookup"><span data-stu-id="21185-162">You'll find all the information that was in the FAQ in this documentation, in context.</span></span>

<span data-ttu-id="21185-163">Si vous recherchez quelque chose que vous ne trouvez pas ici, indiquez à son sujet dans la section **commentaires** ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="21185-163">If you're looking for something that you can't find here, please tell us about it in the **Feedback** section below.</span></span> <span data-ttu-id="21185-164">Nous essayons de répondre à vos commentaires dans les 24 heures.</span><span class="sxs-lookup"><span data-stu-id="21185-164">We try to respond to your feedback within 24 hours.</span></span>

<span data-ttu-id="21185-165">Par ailleurs, il existe **toujours** une FAQ relative à la [transition de Skype Entreprise vers Microsoft Teams](FAQ-journey.md).</span><span class="sxs-lookup"><span data-stu-id="21185-165">By the way, we **do** still have an FAQ for the [Journey from Skype for Business to Microsoft Teams](FAQ-journey.md).</span></span> 
