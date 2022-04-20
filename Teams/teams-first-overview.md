---
title: Déployer Microsoft Teams d’abord
author: LaszloSomi
ms.author: lsomi
manager: swerth
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: lsomi
ms.localizationpriority: medium
search.appverid: MET150
description: Utilisez ces conseils pour déployer Microsoft Teams comme première charge de travail Microsoft 365 ou Office 365.
ROBOTS: NOINDEX, NOFOLLOW
appliesto:
- Microsoft Teams
ms.openlocfilehash: f6dba57003aaa58b9d0b72e7e866da261bed578e
ms.sourcegitcommit: 1d990582e2deb5f55ba9adada3e17377f792a141
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/19/2022
ms.locfileid: "64922685"
---
# <a name="roll-out-microsoft-teams-first"></a>Déployer Microsoft Teams d’abord

Microsoft Teams pouvez aider vos employés à rester connectés et à collaborer les uns avec les autres, en particulier en cette période sans précédent où le travail à distance est une réalité pour les employés du monde entier. La possibilité de discuter, d’effectuer des réunions vidéo et de collaborer sur Office documents au sein de Teams peut aider les entreprises à rester productives. Que vous soyez une petite entreprise, une entreprise à but non lucratif ou une grande organisation, vous pouvez commencer à utiliser Teams comme première charge de travail dans Microsoft 365 ou Office 365 suite avant de déployer tout autre application Office ou service.

Cet article détaille les considérations que vous devez prendre en compte avec l’approche « Teams First ».

> [!IMPORTANT]
> Bien que Teams puisse être la première charge de travail déployée dans le cloud de votre organisation, le déploiement de Teams doit faire partie de votre stratégie globale de déploiement cloud.

Si vous avez déjà déployé d’autres services Microsoft 365 ou Office 365 et que Teams est votre prochaine charge de travail à déployer (au lieu du premier), commencez par [la procédure de déploiement Teams](./deploy-overview.md).

## <a name="start-here"></a>Démarrez ici

Pour commencer à utiliser votre Teams premier déploiement, vous devez respecter au minimum certaines conditions préalables. La liste suivante indique ce que vous devez avoir en place pour votre organisation avant que Teams puisse être activé :

1.  Une organisation Microsoft 365 ou Office 365 configurée avec votre nom de domaine

2.  Azure Active Directory connectivité (connexion AAD) ou une solution de synchronisation d’identité cloud similaire , avec tous les attributs requis synchronisés avec votre locataire  
    Pour comprendre les attributs synchronisés avec AAD synchronisation, lisez [Azure AD Connecter synchronisation : Attributs synchronisés avec Azure Active Directory](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)

3.  Licences utilisateur appropriées attribuées pour Teams  
    Pour comprendre Teams licences, lisez [Microsoft Teams description du service](/office365/servicedescriptions/teams-service-description).

4.  Réseau de l’organisation préparé pour Teams  
    Pour comprendre la préparation du réseau, lisez [Préparer le réseau de votre organisation pour Teams](prepare-network.md).

5.  Autorisez l’accès réseau aux Exchange, SharePoint et OneDrive Entreprise dans Microsoft 365 ou Office 365 : [url Office 365 et plages d’adresses IP](/office365/enterprise/urls-and-ip-address-ranges).

> [!NOTE]
> Les locataires créés après le 1er septembre 2019 sont approvisionnés en mode Teams uniquement.
> 
> [!IMPORTANT]
> Si vous avez Skype Entreprise Server déployé et que votre locataire a été provisionné après le 1er septembre 2019, contactez le support pour activer les fonctionnalités de coexistence pour Teams. Vérifiez que votre « stratégie de mise à niveau à l’échelle de l’organisation » est définie sur « Mode Île » <span class="underline">avant</span> d’attribuer des licences Teams à un utilisateur.

## <a name="migration-starting-points"></a>Points de départ de la migration

Votre parcours vers Microsoft 365 ou Office 365 et fonctionnalités disponibles dans Teams en fonction de votre point de départ et de l’existence d’un serveur Skype Entreprise ou Lync local. Les sections suivantes détaillent les fonctionnalités de base et les options de configuration en plus des prérequis ci-dessus. Nous avons divisé les scénarios de point de départ en rubriques suivantes :

**Configuration Teams** du locataire : les modes client et utilisateur sont utilisés pour contrôler le comportement du destinataire. Ces paramètres peuvent être affectés au niveau du locataire ou de l’utilisateur dans une organisation. Pour en savoir plus, consultez [Coexistence avec Skype Entreprise](coexistence-chat-calls-presence.md).

**Conversation/communication externe dans Teams** : les services de conversation font référence à des conversations d’égal à égal ou de groupe au sein et à l’organisation ou en externe à l’organisation. La communication externe est également appelée fédération dans Skype Entreprise.

**Créer et afficher des réunions dans Teams** : un utilisateur peut toujours créer des réunions en ligne via le complément Outlook Teams et le rendez-vous RTC est disponible dans tous les scénarios une fois que l’utilisateur dispose d’une licence. Teams et Skype Entreprise stockez les informations de calendrier dans la boîte aux lettres Exchange de l’utilisateur. Le serveur Exchange local doit être Exchange Server 2016 CU3 ou version ultérieure pour que le client Teams puisse interagir avec la boîte aux lettres de l’utilisateur. Sans Exchange boîte aux lettres, l’accès à l’icône Calendrier dans Teams n’apparaîtra pas et l’utilisateur ne pourra pas afficher, créer ou modifier des réunions dans le client Teams.

**Fonctionnalités d’appel VoIP/PSTN dans Teams** : l’appel peut être voix sur IP (VoIP) ou réseau téléphonique commuté (RTC). La connectivité VoIP se produit en mode natif entre les clients Teams, tandis que la connectivité RTC se produit lorsqu’un utilisateur compose un numéro de téléphone externe.  

Teams prennent en charge deux types de connectivité RTC. Plan d’appel Microsoft, lorsque Microsoft fournit une infrastructure de téléphonie, y compris le numéro de téléphone d’un utilisateur, ou la configuration du routage direct, où le client fournit la connectivité de téléphonie via un contrôleur de frontière de session (SBC) pour l’utilisateur Teams.  
Pour plus d’informations, consultez [le plan d’appel qui vous convient le mieux et](calling-plan-landing-page.md) [Système téléphonique le routage direct](direct-routing-landing-page.md).

**Teams et canaux de collaboration dans Teams** : Dans Teams, les équipes sont des groupes de personnes réunies pour travailler, projets ou intérêts communs. Teams sont constitués de canaux. Chaque canal est construit autour d’une rubrique, comme « Événements d’équipe », un nom de service, ou simplement pour le plaisir. Les canaux sont l’endroit où vous organisez des réunions, que vous avez des conversations et que vous travaillez ensemble sur des fichiers. Pendant la collaboration

**OneDrive Entreprise (partage de fichiers P2P) dans Teams** : en dehors de Teams et canaux, Teams utilisateurs peuvent partager des fichiers d’égal à égal à l’aide de OneDrive pour les entreprises ou d’autres programmes de fichiers de partage P2P tels que Citrix Files, DropBox, Box et Google Drive. Pour OneDrive pour les entreprises, un utilisateur doit avoir SharePoint licence En ligne attribuée.

**Plateforme d’applications** : les applications fournissent à votre organisation des outils à la disposition des utilisateurs pour tirer le meilleur parti des Teams. Ces applications combinent les fonctionnalités des onglets, des extensions de messagerie, des connecteurs et des bots fournis par Microsoft, créés par un tiers ou par des développeurs de votre organisation.

**Fonctionnalités de sécurité et de conformité :** Teams dispose d’un large éventail d’informations pour vous aider dans les domaines de conformité, notamment les stratégies de rétention, la protection contre la perte de données (DLP), la découverte électronique et la conservation légale pour les canaux, les conversations et les fichiers, la recherche dans les journaux d’audit. Pour en savoir plus, lisez [Sécurité et conformité dans Microsoft Teams](security-compliance-overview.md).  

> [!NOTE]
> Les fonctionnalités eDiscovery avancées nécessitent une licence E5.

[Comparer les options de licence](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).

Découvrez [comment Exchange et Microsoft Teams interagissent](exchange-teams-interact.md) pour savoir quelles fonctionnalités de conformité sont disponibles dans votre scénario.

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a>Organisations **<span class="underline">sans</span>** serveur Skype Entreprise ou Lync

Ce point de départ part du principe que votre organisation n’utilise pas Skype Entreprise ou Lync Server actuellement et que Teams sera votre première application dans Microsoft 365 ou Office 365. Le tableau suivant détaille la configuration de haut niveau et les fonctionnalités de l’utilisateur final pour Teams pour les services principaux.

<table>
<thead>
<tr class="header">
<th>Élément</th>
<th>Remarques</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Configuration Teams du locataire</td>
<td>Teams mode Uniquement, toutes les fonctionnalités de conversation et d’appel sont en Teams uniquement.</td>
</tr>
<tr class="even">
<td>Conversation/ Communication externe dans Teams</td>
<td><p>Communication interne (intra Microsoft 365 ou Office 365) et de conversation externe possible à partir de Teams.</p>
<p><em>Remarque : les entrées DNS doivent être configurées pour l’accès externe. Skype Entreprise enregistrements DNS sont nécessaires, même si vous n’avez pas Skype Entreprise localement, ou en Microsoft 365 ou Office 365, pour autoriser la fédération avec les environnements Lync et Skype Entreprise :<br />
<a href="/office365/enterprise/external-domain-name-system-records">Enregistrements du système de noms de domaine externes</a></em></p></td>
</tr>
<tr class="odd">
<td>Créer et afficher des réunions dans Teams</td>
<td><p>Possibilité de créer des réunions internes et externes via Outlook complément.</p>
<p>La fonctionnalité de numérotation et de numérotation RTC est disponible avec les licences d’audioconférence.</p>
<p>Teams’accès au calendrier nécessite Exchange 2016 CU3+ localement déployé avec Exchange hybride établi : <a href="/exchange/hybrid-deployment/deploy-hybrid">créer un déploiement hybride avec l’Assistant Configuration hybride.</a> </p>

En plus de Exchange configuration hybride, établissez Exchange’authentification OAuth : [Configurez l’authentification OAuth entre les organisations Exchange et Exchange Online](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help). 

</p></td>
</tr>
<tr class="even">
<td>Fonctionnalités d’appel<br />
VoIP /PSTN dans Teams</td>
<td><p>VoIP en interne et en externe au client est disponible.</p>
<p>Les services RTC peuvent être configurés via Téléphone Microsoft Système, ainsi que l’ajout d’un plan d’appel Microsoft ou d’un routage direct.</p></td>
</tr>
<tr class="odd">
<td>collaboration Teams et canaux dans Teams</td>
<td><p>Pour une expérience complète, y compris des fonctionnalités de conformité, une licence SharePoint Online doit être attribuée à l’utilisateur.</p>
<p>La migration de sites SharePoint locaux existants n’est pas nécessaire.</p></td>
</tr>
<tr class="even">
<td>OneDrive Entreprise (partage de fichiers P2P)</td>
<td>OneDrive Entreprise nécessite qu’une licence SharePoint Online soit attribuée à un utilisateur. Sans cette licence, le partage de fichiers d’égal à égal ne sera pas possible.</td>
</tr>
<tr class="odd">
<td>Plateforme d’application</td>
<td>Les utilisateurs pourront utiliser les applications qui sont désignées comme disponibles en fonction des stratégies de votre entreprise.<br />
En savoir plus ici : <a href="/microsoftteams/admin-settings">Paramètres d’administration pour les applications dans Teams</a></td>
</tr>
<tr class="even">
<td>Fonctionnalités de sécurité et de conformité</td>
<td><ul>
<li><p>Des stratégies de rétention sont disponibles.</p></li>
<li><p>eDiscovery et Legal Hold pour la conformité sur les messages de canal sont pris en charge.</p></li>
<li><p>Des stratégies de protection contre la perte de données (DLP) sont disponibles.</p></li>
</ul>
<p>Ensemble de fonctionnalités complet disponible avec Exchange Online; Exchange locale prend en charge la plupart de ces fonctionnalités. Pour obtenir la liste complète, consultez <a href="/MicrosoftTeams/exchange-teams-interact">comment Exchange et Teams interagir</a>.</p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a>Étapes d’activation pour les organisations sans Skype Entreprise ou Lync Server

1.  Respecter les prérequis détaillés dans la section Démarrer ici ci-dessus

2.  Basculer le locataire en mode Teams uniquement (pour les locataires existants uniquement) : [définition de vos paramètres de coexistence et de mise à niveau](setting-your-coexistence-and-upgrade-settings.md).

3.  Configurez votre locataire conformément aux stratégies commerciales/d’entreprise de votre entreprise : [gérez Microsoft Teams paramètres de votre organisation](enable-features-office-365.md).

4.  Déployer le client Teams sur vos utilisateurs : [obtenir des clients pour Teams](get-clients.md)

5.  Piloter votre programme d’adoption  
    [Adopter Microsoft Teams](adopt-microsoft-teams-landing-page.md)
    
    [Liste de contrôle de démarrage rapide pour l’adoption de Microsoft Teams](teams-adoption-quick-start-checklist.md)

6.  Commencer à planifier le déplacement d’autres charges de travail vers Microsoft 365 ou Office 365

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a>Organisations **<span class="underline">avec</span>** serveur Skype Entreprise ou Lync

Ce point de départ suppose que votre organisation utilise Skype Entreprise serveur local 2019 ou 2015+ ou Lync 2013+. Nous avons déjà des conseils complets pour les organisations qui migrent de serveurs locaux vers Teams et il doit être suivi pour ces scénarios. Ce guide est spécifique au scénario qui Teams est la première application que vous utilisez dans Microsoft 365 ou Office 365. Le tableau suivant détaille la configuration de haut niveau et les fonctionnalités de l’utilisateur final pour Teams pour les services principaux.

<table>
<thead>
<tr class="header">
<th>Élément</th>
<th>Remarques</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Configuration Teams du locataire</td>
<td>Mode Îles.</td>
</tr>
<tr class="even">
<td>Conversation/ Communication externe dans Teams</td>
<td>Interne au sein de votre propre locataire uniquement, la communication externe (fédération) se fait via votre déploiement de serveur Skype Entreprise ou Lync.</td>
</tr>
<tr class="odd">
<td>Créer et afficher des réunions dans Teams</td>
<td><p>Possibilité de créer des réunions internes et externes via Outlook complément.</p>
<p>La fonctionnalité de numérotation et de numérotation RTC est disponible avec les licences d’audioconférence.</p>
<p>Teams l’accès au calendrier nécessite Exchange CU3+ 2016 en local déployé avec Exchange hybride établi :<br />
<a href="/exchange/hybrid-deployment/deploy-hybrid">Créez un déploiement hybride avec l’Assistant Configuration hybride.</a></p>
<p>L’administrateur peut contrôler le complément Skype Entreprise Outlook via l’attribut PreferredMeetingProviderForIslandsMode de la stratégie de réunion Teams :<a href="/powershell/module/skype/set-csteamsmeetingpolicy"> set-csteamsmeetingpolicy</a>.</p> 
</td>
</tr>
<tr class="even">
<td>Fonctionnalités d’appel<br />
VoIP /PSTN dans Teams</td>
<td><p>VoIP en interne pour le locataire est disponible.</p>
<p>Les services PSTN ou Forfait d’appel ne sont pas disponibles tant que l’utilisateur n’est pas déplacé vers Teams seule expérience.</p></td>
</tr>
<tr class="odd">
<td>collaboration Teams et canaux dans Teams</td>
<td><p>Pour une expérience complète, y compris des fonctionnalités de conformité, une licence SharePoint Online doit être attribuée à l’utilisateur.</p>
<p>La migration de sites SharePoint locaux existants n’est pas nécessaire.</p></td>
</tr>
<tr class="even">
<td>OneDrive Entreprise (partage de fichiers P2P)</td>
<td>OneDrive Entreprise nécessite qu’une licence SharePoint Online soit attribuée à un utilisateur. Sans cette licence, le partage de fichiers par pair ne sera pas possible.</td>
</tr>
<tr class="odd">
<td>Plateforme d’application</td>
<td>Les utilisateurs pourront utiliser les applications qui sont désignées comme disponibles en fonction des stratégies de votre entreprise.<br />
En savoir plus ici : <a href="/microsoftteams/admin-settings">Paramètres d’administration pour les applications dans Teams</a></td>
</tr>
<tr class="even">
<td>Fonctionnalités de sécurité et de conformité</td>
<td><ul>
<li><p>Des stratégies de rétention sont disponibles.</p></li>
<li><p>eDiscovery et Legal Hold pour la conformité sur les messages de canal sont pris en charge.</p></li>
<li><p>Des stratégies de protection contre la perte de données (DLP) sont disponibles.</p></li>
</ul>
<p>Ensemble de fonctionnalités complet disponible avec Exchange Online; Exchange locale prend en charge la plupart de ces fonctionnalités. Pour obtenir la liste complète, consultez <a href="/MicrosoftTeams/exchange-teams-interact">comment Exchange et Teams interagir.</a></p>
<ul>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a>Étapes d’activation pour les organisations avec Skype Entreprise Server  

1.  Respectez les prérequis détaillés dans la section Démarrer ici ci-dessus.

2.  Basculer le locataire en mode Îles (pour les locataires approvisionnés après le 1er/09/2019, contactez le support technique pour apporter cette modification)  
    [Configuration de vos paramètres de coexistence et de mise à niveau](setting-your-coexistence-and-upgrade-settings.md)

3.  Configurer votre locataire conformément aux stratégies commerciales/d’entreprise de votre entreprise  
    [Gérer les paramètres de Microsoft Teams pour votre organisation](enable-features-office-365.md)

4.  Déployer le client Teams  
    [Obtenir des clients pour Teams](get-clients.md)

5.   Piloter votre programme d’adoption  
    [Adopter Microsoft Teams](adopt-microsoft-teams-landing-page.md)<br/>
    [Liste de contrôle de démarrage rapide pour l’adoption de Microsoft Teams](teams-adoption-quick-start-checklist.md)

6.  Commencer à planifier le déplacement d’autres charges de travail vers Microsoft 365 ou Office 365

7.  Établir Skype Entreprise hybride et suivre les chemins de mise à niveau recommandés pour les serveurs Skype Entreprise et Lync  
    [Effectuer une mise à niveau de Skype Entreprise localement vers Teams](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a>Instruction closing

Microsoft Teams peut être un élément permettant à votre organisation de rassembler tous les employés, les travailleurs de l’information et les travailleurs de première ligne sur une même plateforme. Vous pouvez [commencer](https://products.office.com/microsoft-teams/group-chat-software) aujourd’hui. Vous pouvez rester en contact avec toutes nos dernières annonces et mises à jour mensuelles des produits [ici](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog).

En outre, étant donné que les entreprises du monde entier gèrent la situation actuelle du COVID-19, nous avons créé une série de contenus qui vous aideront à utiliser Teams pour l’impact maximal dans votre organisation.

  - Notre [engagement envers les clients lors du COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)

  - [2 semaines en : ce que nous avons appris sur le travail à distance](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [Remise de réunions et d’événements en ligne](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [Aider les petites et moyennes entreprises à travailler à distance avec Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [Transformation numérique des événements en direct : les observations de Bob Bejan en première ligne](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - [Les 9 principaux moyens que Microsoft IT utilise pour activer le travail à distance de ses employés](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/)

  - [Travailler à distance, rester en sécurité : conseils pour les SIC](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [Aider les enseignants et les étudiants à passer à l’apprentissage à distance](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [Rester productif tout en travaillant à distance avec Microsoft Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a>Informations de référence sur les services de support

Teams s’appuie sur Exchange Online, SharePoint Online, OneDrive Entreprise et Groupes Microsoft 365 pour fournir à vos utilisateurs une Microsoft 365 ou Office 365 expérience. Comme indiqué ci-dessus, Teams fonctionnent sans déploiement complet de ces services, avec des fonctionnalités limitées. Vous pouvez en savoir plus sur Teams et ses conditions préalables ici : [Bienvenue dans Teams](teams-overview.md).

Pour plus d’informations sur chacun des services répertoriés ci-dessus, suivez les liens ci-dessous :

  - Exchange Online est utilisé pour le calendrier des fonctionnalités et le stockage des messages d’égal à égal dans Teams. Pour en savoir plus, consultez [Comment les Exchange et les Teams interagissent](exchange-teams-interact.md)

> [!IMPORTANT]
> Pour Teams interopérabilité avec Exchange localement, vous devez configurer le nouveau protocole d’authentification OAuth Exchange comme décrit dans [Configurer l’authentification OAuth entre les organisations Exchange et Exchange Online](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help).

  - SharePoint est utilisé pour le partage de fichiers dans les canaux, tandis que /OneDrive Entreprise est utilisé pour le partage de fichiers dans la conversation de groupe ou 1:1. Pour en savoir plus, consultez [Comment SharePoint En ligne et OneDrive Entreprise interagir avec Microsoft Teams](sharepoint-onedrive-interact.md).

  - [Groupes Microsoft 365](office-365-groups.md) sont utilisées pour la création/gestion d’équipe et de canal.


## <a name="related-topics"></a>Voir aussi

[Illustrations architecture IT Microsoft Teams et solutions téléphonie](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[Planifier la connectivité hybride entre Skype Entreprise Server et Office 365](/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[Prise en charge des travailleurs distants à l’aide de Teams](support-remote-work-with-teams.md)

[Travailler à distance avec Microsoft 365](https://aka.ms/remote-work)
