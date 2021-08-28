---
title: Déployer et Microsoft Teams d’abord
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
description: Utilisez ces instructions pour déployer votre Microsoft Teams charge de travail Microsoft 365 votre Office 365 travail.
ROBOTS: NOINDEX, NOFOLLOW
appliesto:
- Microsoft Teams
ms.openlocfilehash: c94768c4e95799d0d6f2c98f24a900ac096abd6e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58627036"
---
# <a name="roll-out-microsoft-teams-first"></a>Déployer et Microsoft Teams d’abord

Microsoft Teams peuvent aider vos employés à rester en contact et à collaborer, en particulier au moment du moment où le travail à distance est une réalité d’employés dans le monde entier. La possibilité de discuter, d’utiliser des réunions vidéo et de collaborer sur Office documents au sein de Teams peut aider les entreprises à rester productives. Qu’il s’agit d’une petite entreprise, d’une association ou d’une grande organisation, vous pouvez commencer à utiliser Teams comme première charge de travail au sein de la suite Microsoft 365 ou Office 365 avant de déployer un autre application Office ou service.

Cet article détaille les considérations que vous devez prendre en considération avec l’approche « Teams première ».

> [!IMPORTANT]
> Bien Teams pouvez être la première charge de travail déployée dans le cloud au niveau de votre organisation, le déploiement d’Teams devrait faire partie de votre stratégie de déploiement globale dans le cloud.

Si vous avez déjà déployé d’autres services Microsoft 365 ou Office 365 et Teams est votre prochaine charge de travail à déployer (au lieu de la première), commencez par découvrir comment déployer [Teams.](./deploy-overview.md)

## <a name="start-here"></a>Démarrez ici

Pour commencer à travailler avec votre Teams premier déploiement, vous devez répondre à au moins quelques conditions préalables. La liste suivante indique ce que vous devez mettre en place pour votre organisation pour Teams’être activée :

1.  Organisation Microsoft 365 ou Office 365 configurée avec votre nom de domaine

2.  Azure Active Directory connectivité (connexion AAD) ou solution de synchronisation d’identité de cloud similaire, avec tous les attributs requis synchronisés avec votre client  
    Pour comprendre les attributs synchronisés avec la synchronisation AAD, lisez [Azure AD Connecter synchronisation : Attributs synchronisés avec](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized) les Azure Active Directory

3.  Licences utilisateur appropriées affectées à Teams  
    Pour comprendre Teams de licences, lisez Microsoft Teams [description du service.](/office365/servicedescriptions/teams-service-description)

4.  Le réseau de l’organisation est préparé pour l’Teams  
    Pour comprendre la préparation du réseau, lisez Préparer le réseau [de votre organisation pour l’Teams.](prepare-network.md)

5.  Autoriser l’accès réseau à Exchange, SharePoint et OneDrive Entreprise dans Microsoft 365 ou Office 365 : Office 365 [url et plages d’adresses IP.](/office365/enterprise/urls-and-ip-address-ranges)

> [!NOTE]
> Les locataires créés après le 1er septembre 2019 sont Teams mode d’accès uniquement.
> 
> [!IMPORTANT]
> Si vous avez Skype Entreprise Server et que votre client a été mis en service après le 1er septembre 2019, contactez le support technique pour activer les fonctionnalités de coexistence pour Teams. Assurez-vous que votre « stratégie de mise <span class="underline"></span> à niveau à l’échelle de l’organisation » est définie sur « mode Île » avant d’affecter Teams licences à un utilisateur.

## <a name="migration-starting-points"></a>Points de départ de la migration

Votre chemin vers Microsoft 365 ou Office 365 fonctionnalités disponibles dans Teams en fonction de votre point de départ et de l’existence d’un serveur Skype Entreprise ou Lync local. Les sections suivantes duivent les fonctionnalités de base et les options de configuration, en plus des conditions préalables ci-dessus. Nous avons décomposé les scénarios de point de départ des rubriques suivantes :

**Configuration Teams** client : les modes utilisateur et client sont utilisés pour contrôler le comportement du destinataire. Ces paramètres peuvent être affectés au niveau du client ou de l’utilisateur dans une organisation. Pour en savoir plus, lisez [Coexistence avec Skype Entreprise.](coexistence-chat-calls-presence.md)

**Conversation / Communication externe dans Teams**: les services de conversation font référence à des conversations d’égal à égal ou de groupe au sein et à l’organisation, ou externes à l’organisation. La communication externe est également appelée fédération dans Skype Entreprise.

Créer et afficher des réunions dans Teams : un utilisateur peut toujours créer des réunions en ligne via le composant logiciel Outlook Teams et que la connexion RSTN est disponible dans tous les **scénarios** une fois l’utilisateur titulaire d’une licence. Teams et Skype Entreprise d’informations de calendrier dans la boîte aux lettres de l’Exchange utilisateur. Sur un serveur Exchange doit être Exchange Server 2016 CU3 ou une interface supérieure pour que le client Teams puisse interagir avec la boîte aux lettres de l’utilisateur. Sans Exchange boîte aux lettres, l’icône Calendrier de Teams ne s’affiche pas et les utilisateurs ne pourront pas afficher, créer ou modifier des réunions dans le client Teams.

**Fonctionnalités d’appel VoIP/PSTN** dans Teams : l’appel peut être de voix sur IP (VoIP) ou de réseau téléphonique commuté (PSTN). La connectivité VoIP se produit en natif entre Teams clients, tandis qu’une connectivité RSTN se produit lorsqu’un utilisateur compose un numéro de téléphone extérieur.  

Teams deux types de connectivité PSTN. Microsoft Calling Plan, lorsque Microsoft fournit une infrastructure téléphonique comprenant le numéro de téléphone d’un utilisateur, ou une configuration de routage direct, où le client fournit la connectivité téléphonique sur un contrôleur de session border controller (SBC) pour l’Teams utilisateur.  
Pour en savoir plus, [lisez quel plan d’appels](calling-plan-landing-page.md) vous est le mieux [? Système téléphonique routage direct.](direct-routing-landing-page.md)

**Teams la collaboration** dans les canaux Teams : dans Teams, les équipes sont des groupes de personnes rassemblées pour du travail, des projets ou des intérêts communs. Teams sont composés de canaux. Chaque canal est créé autour d’un sujet( par exemple, « Événements d’équipe », d’un nom de service ou tout simplement pour le plaisir). Les canaux sont l’endroit où vous organisez des réunions, organisez des conversations et travaillez ensemble sur des fichiers. Pendant la collaboration

OneDrive Entreprise (partage de fichiers **P2P)** dans Teams : en dehors de Teams et de canaux, les utilisateurs de Teams peuvent partager des fichiers d’égal à égal à l’aide de OneDrive Entreprise ou d’autres programmes de partage de fichiers P2P tels que Citrix Files, Dropbox, Box et Google Drive. Pour OneDrive entreprise, un utilisateur doit avoir une licence SharePoint Online.

**Plateforme d’application**: les applications offrent à votre organisation des outils pré-pratiques pour vous aider à mieux Teams. Ces applications combinent les fonctionnalités des onglets, des extensions de messagerie, des connecteurs et des bots fournis par Microsoft, par un tiers ou par des développeurs de votre organisation.

Fonctionnalités de sécurité et de conformité : **Teams** dispose d’un vaste éventail d’informations pour vous aider dans les domaines de conformité, notamment les stratégies de rétention, la protection contre la perte de données, la découverte électronique et la conservation légale des canaux, des conversations et des fichiers, et la recherche dans le journal d’audit. Pour en savoir plus, [lisez Sécurité et conformité dans Microsoft Teams.](security-compliance-overview.md)  

> [!NOTE]
> Les fonctionnalités de découverte électronique avancée nécessitent une licence E5.

[Comparer les options de licence.](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)

Découvrez [comment les Exchange et les Microsoft Teams](exchange-teams-interact.md) d’interagir pour découvrir les fonctionnalités de conformité disponibles dans votre scénario.

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a>Organisations **<span class="underline">sans</span>** Skype Entreprise ou Lync Server

Ce point de départ suppose que votre organisation n’utilise pas Skype Entreprise ou Lync Server actuellement et Teams sera votre première application dans Microsoft 365 ou Office 365. Le tableau suivant détaille la configuration de haut niveau et les capacités des utilisateurs finaux pour Teams services principaux.

<table>
<thead>
<tr class="header">
<th>Élément</th>
<th>Remarques</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Configuration Teams client</td>
<td>Teams Seul le mode, toutes les fonctionnalités de conversation et d’appel sont Teams uniquement.</td>
</tr>
<tr class="even">
<td>Conversation / Communication externe dans Teams</td>
<td><p>Communication interne (intra Microsoft 365 ou Office 365) et communication de conversation externe à partir d’Teams.</p>
<p><em>Remarque : les entrées DNS doivent être configurées pour l’accès externe. Skype Entreprise Les enregistrements DNS sont nécessaires même si vous n’avez pas Skype Entreprise en local, ou dans Microsoft 365 ou Office 365, pour autoriser la fédération avec les environnements Lync et Skype Entreprise :<br />
<a href="/office365/enterprise/external-domain-name-system-records">Enregistrements système de noms de domaine externes</a></em></p></td>
</tr>
<tr class="odd">
<td>Créer et afficher des réunions dans Teams</td>
<td><p>Possibilité de créer des réunions internes et externes via Outlook-in.</p>
<p>Les fonctionnalités de connexion et d’appel sortant PSTN sont disponibles avec les licences d’audioconférence.</p>
<p>Teams accès au calendrier nécessite Exchange 2016 CU3+ en local déployé avec Exchange hybride établi : créer un déploiement hybride avec l’Assistant <a href="/exchange/hybrid-deployment/deploy-hybrid">Configuration hybride.</a> </p>

Outre une configuration Exchange hybride, établissez l’authentification OAuth Exchange : configurer l’authentification [OAuth](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)entre les Exchange et Exchange Online utilisateurs. 

</p></td>
</tr>
<tr class="even">
<td>Fonctionnalités d’appel<br />
VoIP /PSTN dans Teams</td>
<td><p>VoIP en interne et en externe vers le client est disponible.</p>
<p>Les services RSTN peuvent être configurés via Téléphone Microsoft système informatique, ainsi que l’ajout d’un plan d’appel Microsoft ou d’un routage direct.</p></td>
</tr>
<tr class="odd">
<td>Teams collaboration dans les canaux dans Teams</td>
<td><p>Pour une expérience complète, y compris des fonctionnalités de conformité, une SharePoint Online doit être attribuée à l’utilisateur.</p>
<p>La migration de sites locaux SharePoint n’est pas nécessaire.</p></td>
</tr>
<tr class="even">
<td>OneDrive Entreprise (partage de fichiers P2P)</td>
<td>OneDrive Entreprise nécessite qu’un utilisateur soit affecté SharePoint licence Online. Sans cette licence, le partage de fichiers d’égal à égal ne sera pas possible.</td>
</tr>
<tr class="odd">
<td>Plateforme des applications</td>
<td>Les utilisateurs pourront utiliser les applications désignées disponibles en fonction des stratégies de votre entreprise.<br />
En savoir plus ici : <a href="/microsoftteams/admin-settings">Paramètres d’administration des applications dans Teams</a></td>
</tr>
<tr class="even">
<td>Fonctionnalités de sécurité et de conformité</td>
<td><ul>
<li><p>Des stratégies de rétention sont disponibles.</p></li>
<li><p>EDiscovery et la mise en attente légale pour la conformité des messages de canal sont pris en charge.</p></li>
<li><p>Des stratégies de protection contre la perte de données (DLP) sont disponibles.</p></li>
</ul>
<p>Jeu de fonctionnalités complet disponible avec Exchange Online ; Exchange local prend en charge la plupart de ces fonctionnalités. Pour obtenir la liste complète, consultez <a href="/MicrosoftTeams/exchange-teams-interact">comment les Exchange et les Teams interagissent.</a></p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a>Étapes d’enablement pour les organisations sans Skype Entreprise ou Lync Server

1.  Répondre aux conditions préalables détaillées dans la section Démarrer ici ci-dessus

2.  Basculez le client en Teams uniquement (pour les clients existants uniquement) : Définition de vos paramètres de coexistence et [de mise à niveau.](setting-your-coexistence-and-upgrade-settings.md)

3.  Configurez votre client conformément aux stratégies de votre entreprise ou de votre entreprise : gérez les paramètres Microsoft Teams [pour votre organisation.](enable-features-office-365.md)

4.  Déployer le client Teams client pour vos utilisateurs : [obtenir des clients pour Teams](get-clients.md)

5.  Pilotez votre programme d’adoption  
    [Adopter Microsoft Teams](adopt-microsoft-teams-landing-page.md)
    
    [Liste de contrôle de démarrage rapide pour l’adoption de Microsoft Teams](teams-adoption-quick-start-checklist.md)

6.  Commencez à planifier le déplacement d’autres charges de Microsoft 365 ou Office 365

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a>Organisations **<span class="underline">avec</span>** Skype Entreprise ou Lync Server

Ce point de départ suppose que votre organisation utilise Skype Entreprise 2019, 2015 et Lync 2013+ en local. Nous avons déjà d’importantes recommandations concernant la migration des serveurs locaux vers Teams organisations, qui doivent être suivies pour ces scénarios. Ces instructions sont spécifiques au scénario Teams’application que vous utilisez en Microsoft 365 ou Office 365. Le tableau suivant détaille la configuration de haut niveau et les capacités des utilisateurs finaux pour Teams services principaux.

<table>
<thead>
<tr class="header">
<th>Élément</th>
<th>Remarques</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Configuration Teams client</td>
<td>Mode Îles.</td>
</tr>
<tr class="even">
<td>Conversation / Communication externe dans Teams</td>
<td>En interne uniquement au sein de votre propre client, les communications externes (fédération) sont accessibles via votre Skype Entreprise ou votre serveur Lync.</td>
</tr>
<tr class="odd">
<td>Créer et afficher des réunions dans Teams</td>
<td><p>Possibilité de créer des réunions internes et externes via Outlook-in.</p>
<p>Les fonctionnalités de connexion et d’appel sortant PSTN sont disponibles avec les licences d’audioconférence.</p>
<p>Teams accès au calendrier nécessite Exchange 2016 CU3+ en local déployé avec une version Exchange hybride établie :<br />
<a href="/exchange/hybrid-deployment/deploy-hybrid">Créez un déploiement hybride à l’aide de l’Assistant Configuration hybride.</a></p>
<p>Un administrateur peut contrôler le Skype Entreprise Outlook par le biais de l’attribut PreferredMeetingProviderForIslandsMode de la stratégie de réunion Teams :<a href="/powershell/module/skype/set-csteamsmeetingpolicy"> set-csteamsmeetingpolicy.</a></p> 
</td>
</tr>
<tr class="even">
<td>Fonctionnalités d’appel<br />
VoIP /PSTN dans Teams</td>
<td><p>VoIP en interne pour le client est disponible.</p>
<p>Les services PSTN ou Calling Plan ne sont pas disponibles tant que l’utilisateur n’a pas été déplacé vers Teams expérience uniquement.</p></td>
</tr>
<tr class="odd">
<td>Teams collaboration dans les canaux dans Teams</td>
<td><p>Pour une expérience complète, y compris des fonctionnalités de conformité, une SharePoint Online doit être attribuée à l’utilisateur.</p>
<p>La migration de sites locaux SharePoint n’est pas nécessaire.</p></td>
</tr>
<tr class="even">
<td>OneDrive Entreprise (partage de fichiers P2P)</td>
<td>OneDrive Entreprise nécessite qu’un utilisateur soit affecté SharePoint licence Online. Sans cette licence, le partage de fichiers entre homologues ne sera pas possible.</td>
</tr>
<tr class="odd">
<td>Plateforme des applications</td>
<td>Les utilisateurs pourront utiliser les applications désignées disponibles en fonction des stratégies de votre entreprise.<br />
En savoir plus ici : <a href="/microsoftteams/admin-settings">Paramètres d’administration des applications dans Teams</a></td>
</tr>
<tr class="even">
<td>Fonctionnalités de sécurité et de conformité</td>
<td><ul>
<li><p>Des stratégies de rétention sont disponibles.</p></li>
<li><p>EDiscovery et la mise en attente légale pour la conformité des messages de canal sont pris en charge.</p></li>
<li><p>Des stratégies de protection contre la perte de données (DLP) sont disponibles.</p></li>
</ul>
<p>Jeu de fonctionnalités complet disponible avec Exchange Online ; Exchange local prend en charge la plupart de ces fonctionnalités. Pour consulter la liste complète, voir <a href="/MicrosoftTeams/exchange-teams-interact">comment les utilisateurs Exchange et Teams interagir.</a></p>
<ul>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a>Étapes d’activement pour les organisations avec Skype Entreprise Server  

1.  Respectez les conditions préalables détaillées dans la section Démarrer ici ci-dessus.

2.  Basculer vers le mode Îles (pour les locataires mis en service APRÈS le 01/09/2019, contactez le support pour apporter cette modification)  
    [Configuration de vos paramètres de coexistence et de mise à niveau](setting-your-coexistence-and-upgrade-settings.md)

3.  Configurer votre client conformément aux stratégies de votre entreprise  
    [Gérer les paramètres de Microsoft Teams pour votre organisation](enable-features-office-365.md)

4.  Déployer le client Teams client  
    [Obtenir des clients pour Teams](get-clients.md)

5.   Pilotez votre programme d’adoption  
    [Adopter Microsoft Teams](adopt-microsoft-teams-landing-page.md)<br/>
    [Liste de contrôle de démarrage rapide pour l’adoption de Microsoft Teams](teams-adoption-quick-start-checklist.md)

6.  Commencez à planifier le déplacement d’autres charges de Microsoft 365 ou Office 365

7.  Établissez Skype Entreprise hybride et suivez les chemins de mise à niveau recommandés pour Skype Entreprise serveurs Lync  
    [Mettre à niveau Skype Entreprise locaux vers Teams](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a>Déclaration de clôture

Microsoft Teams peut permettre à votre organisation de rassembler l’ensemble des employés, des travailleurs de l’information et des employés en ligne, sur une seule plateforme. Vous pouvez [commencer dès aujourd’hui.](https://products.office.com/microsoft-teams/group-chat-software) Vous pouvez rester en contact avec toutes nos dernières annonces et mises à jour mensuelles de [produits ici.](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog)

Par ailleurs, étant donne lieu à la gestion de l’état actuel de COVID-19 par des entreprises du monde entier, nous avons créé une série de contenus qui vous aideront à utiliser Teams pour un impact maximal sur votre organisation.

  - Notre [engagement auprès des clients pendant la période COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)

  - [2 semaines en : ce que nous avons appris sur le travail à distance](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [Fournir des réunions et des événements en ligne](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [Aider les petites et moyennes entreprises à travailler à distance avec Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [Transformation numérique d’événements en direct : les observations d’Bob Bejan à partir de la première ligne](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - [Les 9 principaux moyens que Microsoft IT utilise pour activer le travail à distance de ses employés](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/)

  - [Travailler à distance, rester en sécurité : conseils pour les cisos](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [Aider les enseignants et les étudiants à basculer vers l’apprentissage à distance](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [Rester productif tout en travaillant à distance avec Microsoft Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a>Référence des services d’assistance technique

Teams s’appuie sur les groupes Exchange Online, SharePoint Online, OneDrive Entreprise et Microsoft 365 pour offrir à vos utilisateurs une expérience d’Microsoft 365 ou de Office 365 entièrement intégrée. Comme indiqué ci-dessus, Teams fonctionne sans un déploiement complet de ces services, avec des fonctionnalités limitées. Pour en savoir plus sur Teams et ses conditions préalables, voir : [Bienvenue dans Teams.](teams-overview.md)

Pour plus d’informations sur chacun des services répertoriés ci-dessus, suivez les liens ci-dessous :

  - Exchange Online est utilisé pour les fonctionnalités de calendrier et le stockage de messages d’égal à égal dans Teams. Pour en savoir plus, [lisez comment Exchange et comment Teams interagissez](exchange-teams-interact.md)

> [!IMPORTANT]
> Pour Teams opation avec Exchange locale, vous devez configurer le nouveau protocole d’authentification OAuth Exchange, comme décrit dans la procédure Configurer l’authentification [OAuth](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)entre les organisations Exchange et Exchange Online.

  - SharePoint est utilisé pour le partage de fichiers dans les canaux, tandis que /OneDrive Entreprise est utilisé pour le partage de fichiers dans une conversation en tête-à-tête ou en groupe. Pour en savoir plus, [lisez comment SharePoint En ligne et OneDrive Entreprise interagissez avec Microsoft Teams.](sharepoint-onedrive-interact.md)

  - [Microsoft 365 groupes sont](office-365-groups.md) utilisés pour la création/gestion d’équipes et de canaux.


## <a name="related-topics"></a>Rubriques connexes

[Illustrations architecture IT Microsoft Teams et solutions téléphonie](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[Planifier la connectivité hybride entre Skype Entreprise Server et Office 365](/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[Prise en charge des travailleurs à distance à l’aide Teams](support-remote-work-with-teams.md)

[Travailler à distance avec les Microsoft 365](https://aka.ms/remote-work)
