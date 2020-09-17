---
title: Commencez par déployer Microsoft teams
author: LaszloSomi
ms.author: lsomi
manager: swerth
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: lsomi
localization_priority: Normal
search.appverid: MET150
description: Suivez ces instructions pour déployer Microsoft teams en tant que premier Microsoft 365 ou Workload 365.
ROBOTS: NOINDEX, NOFOLLOW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2f7acdfb092e74ae5e10e818b4007c4e22762a36
ms.sourcegitcommit: e773823a3f71efb6eee3bcbc928f1fee24c9381c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950860"
---
# <a name="roll-out-microsoft-teams-first"></a>Commencez par déployer Microsoft teams

Microsoft teams permet à vos employés de rester connectés et de collaborer entre eux, en particulier dans le temps sans précédent où le Bureau à distance est une réalité de personnes dans le monde entier. Être en mesure de discuter, faire des réunions vidéo et collaborer sur des documents Office dans teams peut aider les entreprises à rester productifs. Qu’il s’agisse d’une petite entreprise, d’une entreprise à but non lucratif ou d’une grande entreprise, vous pouvez commencer à utiliser teams comme première charge de travail dans Microsoft 365 ou la suite Office 365 avant de déployer une application ou un service Office.

Cet article décrit les éléments à prendre en compte lors de l’approche « commencer par Teams ».

> [!IMPORTANT]
> Bien que les équipes puissent être déployées sur le premier Cloud de votre organisation, le déploiement d’équipes devrait faire partie de votre stratégie de déploiement de Cloud globale.

Si vous avez déjà déployé d’autres services Microsoft 365 ou Office 365 et que teams est votre prochain travail de déploiement (plutôt que le premier), commencez par [déployer teams](How-to-roll-out-teams.md).

## <a name="start-here"></a>Démarrez ici

Pour commencer à utiliser votre premier déploiement de Microsoft Teams, vous devez effectuer une réunion au minimum. La liste suivante indique les éléments à mettre en place pour votre organisation afin que les équipes puissent être activées :

1.  Organisation Microsoft 365 ou Office 365 configurée avec votre nom de domaine

2.  Une solution de synchronisation Azure Active Directory (AAD Connect) ou d’identité Cloud similaire, avec tous les attributs requis synchronisés avec votre client  
    Pour comprendre les attributs synchronisés avec la synchronisation AAD, voir [synchronisation d’Azure ad Connect : attributs synchronisés avec Azure Active Directory](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)

3.  Licences utilisateur appropriées affectées aux équipes  
    Pour comprendre les licences d’équipe, voir [Description du service Microsoft teams](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).

4.  Réseau de l’organisation préparé pour teams  
    Pour mieux comprendre la préparation du réseau, voir [préparer le réseau de votre organisation pour teams](prepare-network.md).

5.  Autorisez l’accès réseau à Exchange, SharePoint et OneDrive entreprise dans Microsoft 365 ou Office 365 : [URL et plages d’adresses IP d’office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).

> [!NOTE]
> Les clients créés après le 1er septembre 2019 sont configurés en mode équipes uniquement.
> 
> [!IMPORTANT]
> Si vous avez déployé Skype entreprise Server et que votre client a été approvisionné après le 1er septembre 2019, contactez le support technique pour activer les fonctionnalités de coexistence pour Teams. Assurez-vous que votre « stratégie de mise à niveau de l’organisation » est définie sur « mode insulaire » <span class="underline">avant</span> d’affecter des licences teams à un utilisateur.

## <a name="migration-starting-points"></a>Points de départ de la migration

Le passage à Microsoft 365 ou Office 365 et aux fonctionnalités disponibles dans teams en fonction de votre point de départ et de l’existence de Skype entreprise ou de Lync Server. Les sections suivantes décrivent en détail les fonctionnalités de base et les options de configuration, en plus de celles préalables ci-dessus. Nous avons scindé les scénarios de point de départ aux rubriques suivantes :

**Configuration des équipes de client**: les modes client et utilisateur permettent de contrôler le comportement du destinataire. Ces paramètres peuvent être affectés au niveau du client ou au niveau de l’utilisateur dans une organisation. Pour en savoir plus, voir [coexistence avec Skype entreprise](coexistence-chat-calls-presence.md).

**Discussions/communications externes dans teams**: les services de chat font référence à des conversations d’égal à égal ou à des conversations de groupe au sein de l’organisation ou à l’extérieur. La communication externe est également appelée Fédération dans Skype entreprise.

**Créer et afficher des réunions dans teams**: un utilisateur peut toujours créer des réunions en ligne via le complément Outlook teams et la fonction de numérotation RTC est disponible dans toutes les situations après la licence de l’utilisateur. Équipes et informations de calendrier de Skype entreprise Store dans la boîte aux lettres Exchange de l’utilisateur. Dans le cas d’un serveur Exchange local, le client Microsoft teams doit 2016 être en mesure d’interagir avec la boîte aux lettres de l’utilisateur. Sans accès à la boîte aux lettres Exchange, l’icône calendrier dans Teams ne s’affiche pas et l’utilisateur ne pourra pas afficher, créer ou modifier des réunions dans le client Teams.

**Fonctions d’appel VoIP/PSTN dans teams**: les appels peuvent être vocaux sur IP (VoIP) ou réseau téléphonique commuté (RTC). La connectivité VoIP s’exécute en mode natif entre les clients Teams, tandis que la connectivité PSTN se produit lorsqu’un utilisateur compose un numéro de téléphone externe.  

Teams prend en charge deux types de connectivité PSTN. Plan d’appel Microsoft, lorsque Microsoft fournit une infrastructure de téléphonie dont le numéro de téléphone pour un utilisateur ou une configuration de routage directe, où le client fournit la connectivité téléphonique par le biais d’un contrôleur de bordure de session (SBC) pour l’utilisateur de teams.  
Pour en savoir plus, consultez [l’offre qui vous convient le mieux ? et le](calling-plan-landing-page.md) [routage direct du système téléphonique](direct-routing-landing-page.md).

**Collaboration sur équipes et canaux dans teams**: en équipe, les équipes sont des groupes de personnes qui ont été réunis pour le travail, les projets ou les centres d’intérêt communs. Les équipes sont composées de canaux. Chaque canal est intégré à un sujet, tel qu’un « événements d’équipe », un nom de service ou un simple plaisir. Les canaux sont l’endroit où vous organisez des réunions, des conversations et travaillez ensemble. Lors de la collaboration

**OneDrive entreprise (partage de fichiers P2P) dans teams**: à l’extérieur des équipes et des canaux, les utilisateurs de teams peuvent partager des fichiers d’égal à égal à l’aide de OneDrive entreprise ou d’autres programmes de fichiers de partage P2P tels que les fichiers Citrix, Dropbox, Box et Google Drive. Pour OneDrive entreprise, un utilisateur doit avoir une licence SharePoint Online affectée.

**Plateforme d’application**: les applications fournissent des outils prédéfinis pour votre organisation afin de tirer le meilleur parti de teams. Ces applications associent les fonctionnalités des onglets, des extensions de messagerie, des connecteurs et des robots proposés par Microsoft, par une tierce partie ou par les développeurs de votre organisation.

**Fonctionnalités de sécurité et de conformité :** Teams dispose d’une large gamme d’informations pour vous aider à utiliser les zones de conformité, notamment les stratégies de rétention, la protection contre la perte de données (DLP), la découverte électronique et la conservation légale pour les canaux, les conversations et les fichiers, la recherche dans le journal d’audit. Pour en savoir plus, voir [sécurité et conformité dans Microsoft teams](security-compliance-overview.md).  

> [!NOTE]
> Les fonctionnalités de eDiscovery avancées nécessitent une licence E5.

[Comparer les options de licence](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).

Découvrez [Comment Exchange et Microsoft teams interagissent](exchange-teams-interact.md) pour découvrir les fonctionnalités de conformité disponibles dans votre scénario.

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a>Organisations **<span class="underline">sans</span>** Skype entreprise ou Lync Server

Ce point de départ part du principe que votre organisation n’utilise pas Skype entreprise ou Lync Server actuellement et que teams sera votre première application dans Microsoft 365 ou Office 365. Le tableau suivant répertorie les fonctionnalités de configuration de haut niveau et d’utilisateur final pour les équipes de services principaux.

<table>
<thead>
<tr class="header">
<th>Élément</th>
<th>Remarques</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Configuration des équipes client</td>
<td>Le mode équipes uniquement, les fonctionnalités de conversation et d’appel ne sont disponibles que dans Teams.</td>
</tr>
<tr class="even">
<td>Discussions/communications externes dans teams</td>
<td><p>Internal (organisation Microsoft 365 ou Office 365) et communications externes possibles depuis Teams.</p>
<p><em>Remarque : les entrées DNS doivent être configurées pour l’accès externe. Les enregistrements DNS de Skype entreprise sont nécessaires même si vous n’avez pas Skype entreprise local ou dans Microsoft 365 ou Office 365, pour autoriser la Fédération avec Lync et les environnements Skype entreprise :<br />
<a href="https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records">Enregistrements système de noms de domaine externes</a></em></p></td>
</tr>
<tr class="odd">
<td>Créer et afficher des réunions dans Microsoft teams</td>
<td><p>Possibilité de créer des réunions internes et externes via le complément Outlook.</p>
<p>Les fonctionnalités de numérotation et de connexion RTC sont disponibles avec les licences de conférence audio.</p>
<p>L’accès au calendrier teams nécessite Exchange 2016 CU3 + local déployé avec Exchange hybride établi : <a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">créer un déploiement hybride à l’aide de l’Assistant Configuration hybride.</a> </p>
<p>En plus de la configuration hybride Exchange, établissez l’authentification OAuth Exchange : <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help"> configurez l’authentification OAuth entre les organisations Exchange et Exchange Online.</p>

</p></td>
</tr>
<tr class="even">
<td>Fonctions d’appel<br />
VoIP/PSTN dans teams</td>
<td><p>VoIP est disponible en interne et en externe sur le client.</p>
<p>Les services RTC peuvent être configurés via le système Microsoft Phone, ainsi que l’ajout d’un plan d’appel Microsoft ou du routage direct.</p></td>
</tr>
<tr class="odd">
<td>Collaborer sur équipes et canaux dans teams</td>
<td><p>Pour une utilisation complète, y compris les fonctionnalités de conformité, une licence SharePoint Online doit être attribuée à l’utilisateur.</p>
<p>La migration de sites SharePoint locaux existants n’est pas requise.</p></td>
</tr>
<tr class="even">
<td>OneDrive entreprise (partage de fichiers P2P)</td>
<td>OneDrive entreprise nécessite l’attribution d’une licence SharePoint Online à un utilisateur. Sans cette licence le partage de fichiers d’égal à égal n’est pas possible.</td>
</tr>
<tr class="odd">
<td>Plateforme d’application</td>
<td>Les utilisateurs pourront utiliser les applications qui sont conçues pour eux conformément aux politiques de votre entreprise.<br />
Pour en savoir plus <a href="https://docs.microsoft.com/microsoftteams/admin-settings">, voir paramètres d’administration des applications dans Microsoft teams</a> .</td>
</tr>
<tr class="even">
<td>Fonctionnalités de sécurité et de conformité</td>
<td><ul>
<li><p>Des stratégies de rétention sont disponibles.</p></li>
<li><p>la découverte électronique et les conservations juridiques pour la conformité aux messages de canal sont prises en charge.</p></li>
<li><p>Des stratégies de protection contre la perte de données (DLP) sont disponibles.</p></li>
</ul>
<p>Ensemble complet des fonctionnalités disponibles avec Exchange Online ; Exchange sur site prend en charge la plupart de ces fonctionnalités. Pour obtenir une liste complète, voir <a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">Comment Exchange et teams interagissent</a>.</p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a>Étapes d’activation pour les organisations sans Skype entreprise ou Lync Server

1.  Répondez aux conditions préalables décrites dans la section début

2.  Basculer le client en mode équipes uniquement (pour les clients existants uniquement) : [définir vos paramètres de coexistence et de mise à niveau](setting-your-coexistence-and-upgrade-settings.md).

3.  Configurez votre client conformément aux politiques de votre entreprise : gérer les [paramètres de Microsoft teams pour votre organisation](enable-features-office-365.md).

4.  Déployer le client teams auprès de vos utilisateurs : [accéder aux clients pour teams](get-clients.md)

5.  Piloter votre programme d’adoption  
    [Adopter Microsoft Teams](adopt-microsoft-teams-landing-page.md)
    
    [Liste de contrôle de démarrage rapide pour l’adoption de Microsoft Teams](teams-adoption-quick-start-checklist.md)

6.  Commencer à planifier déplacer d’autres charges de travail vers Microsoft 365 ou Office 365

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a>Organisations **<span class="underline">avec</span>** Skype entreprise ou Lync Server

Ce point de départ part du principe que votre organisation utilise Skype entreprise 2019 ou 2015 + ou Lync 2013 + Server en local. Nous proposons déjà des recommandations complètes pour les organisations migrant de serveurs locaux vers équipes et elles doivent être suivies dans ces scénarios. Ce guide est spécifique au scénario que teams est la première application utilisée dans Microsoft 365 ou Office 365. Le tableau suivant répertorie les fonctionnalités de configuration de haut niveau et d’utilisateur final pour les équipes de services principaux.

<table>
<thead>
<tr class="header">
<th>Élément</th>
<th>Remarques</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Configuration des équipes client</td>
<td>Mode îlot.</td>
</tr>
<tr class="even">
<td>Discussions/communications externes dans teams</td>
<td>Interne uniquement au sein de votre client, la communication externe (Fédération) est via le déploiement de Skype entreprise ou de Lync Server.</td>
</tr>
<tr class="odd">
<td>Créer et afficher des réunions dans Microsoft teams</td>
<td><p>Possibilité de créer des réunions internes et externes via le complément Outlook.</p>
<p>Les fonctionnalités de numérotation et de connexion RTC sont disponibles avec les licences de conférence audio.</p>
<p>L’accès au calendrier teams nécessite Exchange 2016 CU3 + local déployé avec Exchange hybride établi :<br />
<a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">Créer un déploiement hybride à l’aide de l’Assistant Configuration hybride.</a></p>
<p>L’administrateur peut contrôler le complément Outlook Skype entreprise par le biais de l’attribut PreferredMeetingProviderForIslandsMode de la stratégie de réunion teams :<a href="https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps"> Set-csteamsmeetingpolicy</a>.</p> 
</td>
</tr>
<tr class="even">
<td>Fonctions d’appel<br />
VoIP/PSTN dans teams</td>
<td><p>Le VoIP est disponible en interne sur le client.</p>
<p>Les services RTC ou de plan d’appel ne sont pas disponibles tant que l’utilisateur n’a pas été déplacé vers l’interface uniquement.</p></td>
</tr>
<tr class="odd">
<td>Collaborer sur équipes et canaux dans teams</td>
<td><p>Pour une utilisation complète, y compris les fonctionnalités de conformité, une licence SharePoint Online doit être attribuée à l’utilisateur.</p>
<p>La migration de sites SharePoint locaux existants n’est pas requise.</p></td>
</tr>
<tr class="even">
<td>OneDrive entreprise (partage de fichiers P2P)</td>
<td>OneDrive entreprise nécessite l’attribution d’une licence SharePoint Online à un utilisateur. Sans ce partage de fichier de licence par poste à homologue, vous ne serez pas possible.</td>
</tr>
<tr class="odd">
<td>Plateforme d’application</td>
<td>Les utilisateurs pourront utiliser les applications qui sont conçues pour eux conformément aux politiques de votre entreprise.<br />
Pour en savoir plus <a href="https://docs.microsoft.com/microsoftteams/admin-settings">, voir paramètres d’administration des applications dans Microsoft teams</a> .</td>
</tr>
<tr class="even">
<td>Fonctionnalités de sécurité et de conformité</td>
<td><ul>
<li><p>Des stratégies de rétention sont disponibles.</p></li>
<li><p>la découverte électronique et les conservations juridiques pour la conformité aux messages de canal sont prises en charge.</p></li>
<li><p>Des stratégies de protection contre la perte de données (DLP) sont disponibles.</p></li>
</ul>
<p>Ensemble complet des fonctionnalités disponibles avec Exchange Online ; Exchange sur site prend en charge la plupart de ces fonctionnalités. Pour obtenir la liste complète, voir <a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">Comment Exchange et teams interagissent.</a></p>
<ul>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a>Étapes d’activation pour les organisations avec Skype entreprise Server  

1.  Répondez aux conditions préalables décrites dans la section début here ci-dessus.

2.  Changer de locataire en mode îlots (pour les clients approvisionnés après 9/1/2019, veuillez contacter le support technique pour apporter cette modification)  
    [Configuration de vos paramètres de coexistence et de mise à niveau](setting-your-coexistence-and-upgrade-settings.md)

3.  Configurer votre client conformément aux politiques de votre entreprise  
    [Gérer les paramètres de Microsoft Teams pour votre organisation](enable-features-office-365.md)

4.  Déployer le client teams  
    [Obtenir des clients pour Teams](get-clients.md)

5.   Piloter votre programme d’adoption  
    [Adopter Microsoft Teams](adopt-microsoft-teams-landing-page.md)<br/>
    [Liste de contrôle de démarrage rapide pour l’adoption de Microsoft Teams](teams-adoption-quick-start-checklist.md)

6.  Commencer à planifier déplacer d’autres charges de travail vers Microsoft 365 ou Office 365

7.  Établissement de Skype entreprise hybride et suivi des chemins de mise à niveau recommandés pour les serveurs Skype entreprise et Lync  
    [Mise à niveau de Skype entreprise local vers teams](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a>Instruction de fermeture

Microsoft teams permet à votre organisation de mettre en place tous les employés, travailleurs de l’information et personnes terrain sur une seule plate-forme. Vous pouvez [commencer](https://products.office.com/microsoft-teams/group-chat-software) dès aujourd’hui. Vous pouvez garder le suivi de toutes les dernières annonces et des mises à jour mensuelles de nos [produits.](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog)

Par ailleurs, en tant qu’entreprises dans le monde de la gestion de la situation actuelle COVID-19, nous avons créé une série de contenus qui vous aideront à utiliser les équipes pour un impact maximal sur votre organisation.

  - Notre [engagement pour les clients pendant COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)

  - [2 semaines dans : ce que nous avons appris sur le fonctionnement distant](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [Diffuser des réunions et des événements en ligne](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [Aider les petites et moyennes entreprises à travailler à distance avec Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [Transformation numérique des événements en direct : les observations de Bob Bejan de la Frontline](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - [Les 9 principaux moyens que Microsoft IT utilise pour activer le travail à distance de ses employés](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/)

  - [Travaillez à distance, restez sécurisé ; conseils pour CISOs](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [Aider les enseignants et les étudiants à effectuer la transition vers une formation à distance](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [Rester productif lorsque vous travaillez à distance à l’aide de Microsoft teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a>Support technique services

Teams repose sur les groupes Exchange Online, SharePoint Online, OneDrive entreprise et Microsoft 365 pour fournir aux utilisateurs une connaissance complète de Microsoft 365 ou d’Office 365. Comme indiqué plus haut, teams fonctionne sans le déploiement complet de ces services, avec des fonctionnalités limitées. Pour en savoir plus sur les équipes et ses conditions préalables, consultez la [page Bienvenue dans teams](teams-overview.md).

Pour des détails spécifiques sur chacun des services indiqués ci-dessus, suivez les liens ci-dessous :

  - Exchange Online est utilisé pour les fonctionnalités de calendrier et le stockage des messages d’égal à égal dans Teams. Pour en savoir plus, voir [Comment Exchange et teams interagissent](exchange-teams-interact.md)

> [!IMPORTANT]
> Pour une interopérabilité entre les équipes avec Exchange en local, vous devez configurer le nouveau protocole d’authentification OAuth Exchange comme décrit dans [configurer l’authentification OAuth entre les organisations Exchange et Exchange Online](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help).

  - SharePoint est utilisé pour le partage de fichiers dans les canaux, tandis que/OneDrive entreprise est utilisé pour le partage de fichiers dans 1:1 ou la discussion de groupe. Pour en savoir plus, voir [comment SharePoint Online et OneDrive entreprise interagissent avec Microsoft teams](sharepoint-onedrive-interact.md).

  - Les [groupes Microsoft 365](office-365-groups.md) sont utilisés pour la création et la gestion d’équipes et de canaux.


## <a name="related-topics"></a>Sujets associés

[Illustrations architecture IT Microsoft Teams et solutions téléphonie](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[Planifier la connectivité hybride entre Skype Entreprise Server et Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[Prendre en charge les travailleurs distants avec teams](support-remote-work-with-teams.md)

[Travailler à distance avec Microsoft 365](https://aka.ms/remote-work)
