---
title: Déployer Microsoft Teams En premier
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
description: Utilisez ces instructions pour déployer Microsoft Teams comme première charge de travail Microsoft 365 ou Office 365.
ROBOTS: NOINDEX, NOFOLLOW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 81ecf9a0f963a1be577149c585424c140df2abd5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119353"
---
# <a name="roll-out-microsoft-teams-first"></a>Déployer Microsoft Teams en premier

Microsoft Teams peut aider vos employés à rester en contact et à collaborer, en particulier au moment de l’heure actuelle où le travail à distance est la réalité des employés dans le monde entier. La possibilité de discuter, d’utiliser des réunions vidéo et de collaborer sur des documents Office dans Teams peut aider les entreprises à rester productives. Qu’il s’agit d’une petite entreprise, d’une association ou d’une grande organisation, vous pouvez commencer à utiliser Teams comme première charge de travail dans Microsoft 365 ou la suite Office 365 avant de déployer une autre application ou service Office.

Cet article détaille les considérations que vous devez prendre en considération avec l’approche « Teams First ».

> [!IMPORTANT]
> Bien que Teams puisse être la première charge de travail déployée dans le cloud au niveau de votre organisation, le déploiement d’Équipes doit faire partie de votre stratégie de déploiement globale dans le cloud.

Si vous avez déjà déployé d’autres services Microsoft 365 ou Office 365 et Teams est votre prochaine charge de travail à déployer (au lieu de la première), commencez par découvrir comment déployer [Teams.](./deploy-overview.md)

## <a name="start-here"></a>Démarrez ici

Pour commencer à travailler avec votre déploiement Teams, vous devez au moins respecter certaines conditions préalables. La liste suivante indique ce que vous devez avoir en place pour votre organisation pour que Teams soit activé :

1.  Organisation Microsoft 365 ou Office 365 configurée avec votre nom de domaine

2.  Connectivité Azure Active Directory (connexion AAD) ou solution de synchronisation d’identité de cloud similaire, avec tous les attributs requis synchronisés avec votre client  
    Pour comprendre les attributs synchronisés avec la synchronisation AAD, lisez synchronisation Azure AD Connect : [Attributs synchronisés avec Azure Active Directory](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)

3.  Licences utilisateur appropriées attribuées à Teams  
    Pour comprendre la licence de Teams, lisez [la description du service Microsoft Teams.](/office365/servicedescriptions/teams-service-description)

4.  Le réseau de l’organisation est préparé pour Teams  
    Pour comprendre la préparation du réseau, lisez Préparer le réseau de votre [organisation pour Teams.](prepare-network.md)

5.  Autoriser l’accès réseau à Exchange, Sharepoint et OneDrive Entreprise dans Microsoft 365 ou Office 365 : URL [et plages d’adresses IP Office 365.](/office365/enterprise/urls-and-ip-address-ranges)

> [!NOTE]
> Les locataires créés après le 1er septembre 2019 sont mis en service en mode Teams uniquement.
> 
> [!IMPORTANT]
> Si Skype Entreprise Server est déployé et que votre client a été mis en service après le 1er septembre 2019, contactez le support technique pour activer les fonctionnalités de coexistence pour Teams. Assurez-vous que votre « stratégie de mise <span class="underline"></span> à niveau à l’échelle de l’organisation » est définie sur « mode Île » avant d’affecter des licences Teams à un utilisateur.

## <a name="migration-starting-points"></a>Points de départ de la migration

Votre parcours vers Microsoft 365 ou Office 365 et les fonctionnalités disponibles dans Teams en fonction de votre point de départ et de l’existence d’un serveur Skype Entreprise ou Lync local. Les sections suivantes duivent les fonctionnalités de base et les options de configuration, en plus des conditions préalables ci-dessus. Nous avons décomposé les scénarios de point de départ des rubriques suivantes :

**Configuration des équipes client**: les modes client et utilisateur sont utilisés pour contrôler le comportement du destinataire. Ces paramètres peuvent être affectés au niveau du client ou de l’utilisateur dans une organisation. Pour en savoir plus, lisez [Coexistence avec Skype Entreprise.](coexistence-chat-calls-presence.md)

**Conversation / Communication externe dans Teams**: les services de conversation font référence aux conversations d’égal à égal ou de groupe au sein et à l’organisation, ou externes à l’organisation. La communication externe est également appelée fédération dans Skype Entreprise.

Créer et afficher des réunions dans **Teams**: un utilisateur peut toujours créer des réunions en ligne via le composant logiciel Outlook Teams, et le rendez-vous PSTN est disponible dans tous les scénarios une fois que l’utilisateur dispose d’une licence. Teams et Skype Entreprise stockent des informations de calendrier dans la boîte aux lettres Exchange de l’utilisateur. Le serveur Exchange local doit être Exchange Server 2016 CU3 ou une interface supérieure pour que le client Teams puisse interagir avec la boîte aux lettres de l’utilisateur. Sans accès à la boîte aux lettres Exchange, l’icône Calendrier dans Teams n’apparaît pas et les utilisateurs ne peuvent pas afficher, créer ou modifier des réunions dans le client Teams.

**Fonctionnalités d’appel VoIP/PSTN** dans Teams : l’appel peut être de la voix sur IP (VoIP) ou du réseau téléphonique commuté (PSTN). La connectivité VoIP se produit en natif entre les clients Teams, tandis qu’une connectivité RSTN se produit lorsqu’un utilisateur compose un numéro de téléphone extérieur.  

Teams supporte deux types de connectivité PSTN. Microsoft Calling Plan, lorsque Microsoft fournit une infrastructure téléphonique comprenant le numéro de téléphone d’un utilisateur, ou une configuration de routage direct, où le client fournit la connectivité téléphonique sur un contrôleur de session border controller (SBC) pour l’utilisateur Teams.  
Pour en savoir plus, [lisez le plan d’appels](calling-plan-landing-page.md) qui vous est le plus exact ? et [le routage direct du système téléphonique.](direct-routing-landing-page.md)

**Collaboration sur les équipes** et les canaux dans Teams : Dans Teams, les équipes sont des groupes de personnes rassemblées pour travailler, projets ou intérêts communs. Les équipes sont composés de canaux. Chaque canal est créé autour d’un sujet( par exemple, « Événements d’équipe », d’un nom de service ou tout simplement pour le plaisir). Les canaux sont l’endroit où vous organisez des réunions, organisez des conversations et travaillez ensemble sur des fichiers. Pendant la collaboration

OneDrive Entreprise (partage de fichiers **P2P)** dans Teams : en dehors des équipes et des canaux, les utilisateurs de Teams peuvent partager des fichiers p2P à l’aide de OneDrive Entreprise ou d’autres programmes de partage P2P tels que Citrix Files, Dropbox, Box et Google Drive. Pour OneDrive Entreprise, une licence SharePoint Online doit être attribuée à un utilisateur.

**Plateforme d’application**: les applications offrent des outils pré-pré-pratiques pour votre organisation afin de mieux parti de Teams. Ces applications combinent les fonctionnalités des onglets, des extensions de messagerie, des connecteurs et des bots fournis par Microsoft, par un tiers ou par des développeurs de votre organisation.

**Fonctionnalités de sécurité et de conformité :** Teams dispose d’un large éventail d’informations pour vous aider dans les domaines de conformité, notamment les stratégies de rétention, la protection contre la perte de données, l’eDiscovery et la conservation légale pour les canaux, les conversations et les fichiers, la recherche dans le journal d’audit. Pour en savoir plus, [lisez Sécurité et conformité dans Microsoft Teams.](security-compliance-overview.md)  

> [!NOTE]
> Les fonctionnalités de découverte électronique avancée nécessitent une licence E5.

[Comparer les options de licence.](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)

Découvrez [comment Exchange et Microsoft Teams interagissent](exchange-teams-interact.md) pour découvrir les fonctionnalités de conformité disponibles dans votre scénario.

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a>Organisations **<span class="underline">sans</span>** Skype Entreprise ou Lync Server

Ce point de départ suppose que votre organisation ne utilise pas Skype Entreprise ou Lync Server actuellement et que Teams sera votre première application dans Microsoft 365 ou Office 365. Le tableau suivant détaille la configuration de haut niveau et les capacités des utilisateurs finaux pour Teams pour les services principaux.

<table>
<thead>
<tr class="header">
<th>Élément</th>
<th>Remarques</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Configuration de Teams client</td>
<td>Mode Équipes uniquement, toutes les fonctionnalités de conversation et d’appel sont dans Teams uniquement.</td>
</tr>
<tr class="even">
<td>Conversation / Communication externe dans Teams</td>
<td><p>Communication interne (intra Microsoft 365 ou Office 365) et communication de conversation externe à partir de Teams.</p>
<p><em>Remarque : les entrées DNS doivent être configurées pour l’accès externe. Les enregistrements DNS Skype Entreprise sont nécessaires même si vous n’avez pas Skype Entreprise en local, ou dans Microsoft 365 ou Office 365, pour autoriser la fédération avec les environnements Lync et Skype Entreprise :<br />
<a href="/office365/enterprise/external-domain-name-system-records">Enregistrements système de noms de domaine externes</a></em></p></td>
</tr>
<tr class="odd">
<td>Créer et afficher des réunions dans Teams</td>
<td><p>Possibilité de créer des réunions internes et externes via le add-in Outlook.</p>
<p>Les fonctionnalités PSTN Dial In and Dial out sont disponibles avec les licences d’audioconférence.</p>
<p>L’accès au calendrier Teams nécessite Exchange 2016 CU3+ en local déployé avec Exchange hybride établi : créer un déploiement hybride avec <a href="/exchange/hybrid-deployment/deploy-hybrid">l’Assistant Configuration hybride.</a> </p>
<p>Outre la configuration hybride Exchange, établissez l’authentification OAuth Exchange : Configurer l’authentification OAuth entre les organisations <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help"> Exchange et Exchange Online ».</p>

</p></td>
</tr>
<tr class="even">
<td>Fonctionnalités d’appel<br />
VoIP /PSTN dans Teams</td>
<td><p>VoIP en interne et en externe vers le client est disponible.</p>
<p>Les services RSTN peuvent être configurés via Microsoft Phone System, ainsi que l’ajout d’un plan d’appel Microsoft ou d’un routage direct.</p></td>
</tr>
<tr class="odd">
<td>Collaboration avec les équipes et les canaux dans Teams</td>
<td><p>Pour une expérience complète, y compris des fonctionnalités de conformité, une licence SharePoint Online doit être attribuée à l’utilisateur.</p>
<p>La migration de sites SharePoint locaux existants n’est pas nécessaire.</p></td>
</tr>
<tr class="even">
<td>OneDrive Entreprise (partage de fichiers P2P)</td>
<td>OneDrive Entreprise nécessite qu’une licence SharePoint Online soit attribuée à un utilisateur. Sans cette licence, le partage de fichiers d’égal à égal ne sera pas possible.</td>
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
<li><p>EDiscovery et la recherche légale pour la conformité des messages de canal sont pris en charge.</p></li>
<li><p>Des stratégies de protection contre la perte de données (DLP) sont disponibles.</p></li>
</ul>
<p>Jeu de fonctionnalités complet disponible avec Exchange Online Exchange en local prend en charge la plupart de ces fonctionnalités. Pour obtenir la liste complète, consultez <a href="/MicrosoftTeams/exchange-teams-interact">comment Exchange et Teams interagissent.</a></p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a>Étapes d’activement pour les organisations sans Skype Entreprise ou Lync Server

1.  Répondre aux conditions préalables détaillées dans la section Démarrer ici ci-dessus

2.  Basculez vers le mode Teams uniquement (pour les clients existants uniquement) : Définition de vos paramètres de coexistence et [de mise à niveau.](setting-your-coexistence-and-upgrade-settings.md)

3.  Configurez votre client conformément aux stratégies de votre entreprise ou de votre entreprise : Gérez les [paramètres Microsoft Teams pour votre organisation.](enable-features-office-365.md)

4.  Déployer le client Teams pour vos utilisateurs : [Obtenir des clients pour Teams](get-clients.md)

5.  Pilotez votre programme d’adoption  
    [Adopter Microsoft Teams](adopt-microsoft-teams-landing-page.md)
    
    [Liste de contrôle de démarrage rapide pour l’adoption de Microsoft Teams](teams-adoption-quick-start-checklist.md)

6.  Commencer à planifier le déplacement d’autres charges de travail vers Microsoft 365 ou Office 365

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a>Organisations **<span class="underline">avec</span>** Skype Entreprise ou Lync Server

Ce point de départ suppose que votre organisation utilise Skype Entreprise 2019, 2015 ou Lync 2013+ en local. Nous avons déjà d’importantes recommandations concernant la migration des serveurs locaux vers Teams, qui doivent être suivies pour ces scénarios. Ces instructions sont spécifiques au scénario où Teams est la première application que vous utilisez dans Microsoft 365 ou Office 365. Le tableau suivant détaille la configuration de haut niveau et les capacités des utilisateurs finaux pour Teams pour les services principaux.

<table>
<thead>
<tr class="header">
<th>Élément</th>
<th>Remarques</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Configuration de Teams client</td>
<td>Mode Îles.</td>
</tr>
<tr class="even">
<td>Conversation / Communication externe dans Teams</td>
<td>En interne uniquement au sein de votre propre client, les communications externes (fédération) sont accessibles via votre déploiement Skype Entreprise ou serveur Lync.</td>
</tr>
<tr class="odd">
<td>Créer et afficher des réunions dans Teams</td>
<td><p>Possibilité de créer des réunions internes et externes via le add-in Outlook.</p>
<p>Les fonctionnalités PSTN Dial In and Dial out sont disponibles avec les licences d’audioconférence.</p>
<p>L’accès au calendrier Teams nécessite Exchange 2016 CU3+ en local déployé avec Exchange hybride établi :<br />
<a href="/exchange/hybrid-deployment/deploy-hybrid">Créez un déploiement hybride à l’aide de l’Assistant Configuration hybride.</a></p>
<p>L’administrateur peut contrôler le ajouter Outlook de Skype Entreprise via l’attribut PreferredMeetingProviderForIslandsMode de la stratégie de réunion Teams :<a href="/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps"> set-csteamsmeetingpolicy.</a></p> 
</td>
</tr>
<tr class="even">
<td>Fonctionnalités d’appel<br />
VoIP /PSTN dans Teams</td>
<td><p>VoIP en interne vers le client est disponible.</p>
<p>Les services PSTN ou Forfait d’appels ne sont pas disponibles tant que l’utilisateur n’a pas été déplacé vers l’expérience Teams uniquement.</p></td>
</tr>
<tr class="odd">
<td>Collaboration avec les équipes et les canaux dans Teams</td>
<td><p>Pour une expérience complète, y compris des fonctionnalités de conformité, une licence SharePoint Online doit être attribuée à l’utilisateur.</p>
<p>La migration de sites SharePoint locaux existants n’est pas nécessaire.</p></td>
</tr>
<tr class="even">
<td>OneDrive Entreprise (partage de fichiers P2P)</td>
<td>OneDrive Entreprise nécessite qu’une licence SharePoint Online soit attribuée à un utilisateur. Sans cette licence, le partage de fichiers entre homologues ne sera pas possible.</td>
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
<li><p>EDiscovery et la recherche légale pour la conformité des messages de canal sont pris en charge.</p></li>
<li><p>Des stratégies de protection contre la perte de données (DLP) sont disponibles.</p></li>
</ul>
<p>Jeu de fonctionnalités complet disponible avec Exchange Online Exchange en local prend en charge la plupart de ces fonctionnalités. Pour consulter la liste complète, voir <a href="/MicrosoftTeams/exchange-teams-interact">comment Exchange et Teams interagissent.</a></p>
<ul>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a>Étapes d’enablement pour les organisations avec Skype Entreprise Server  

1.  Respectez les conditions préalables détaillées dans la section Démarrer ici ci-dessus.

2.  Basculer vers le mode Îles (pour les locataires mis en service APRÈS le 01/09/2019, contactez le support pour apporter cette modification)  
    [Configuration de vos paramètres de coexistence et de mise à niveau](setting-your-coexistence-and-upgrade-settings.md)

3.  Configurer votre client conformément aux stratégies de votre entreprise en matière d’entreprise/entreprise  
    [Gérer les paramètres de Microsoft Teams pour votre organisation](enable-features-office-365.md)

4.  Déployer le client Teams  
    [Obtenir des clients pour Teams](get-clients.md)

5.   Pilotez votre programme d’adoption  
    [Adopter Microsoft Teams](adopt-microsoft-teams-landing-page.md)<br/>
    [Liste de contrôle de démarrage rapide pour l’adoption de Microsoft Teams](teams-adoption-quick-start-checklist.md)

6.  Commencer à planifier le déplacement d’autres charges de travail vers Microsoft 365 ou Office 365

7.  Établir Skype Entreprise hybride et suivre les chemins de mise à niveau recommandés pour Skype Entreprise et les serveurs Lync  
    [Mise à niveau de Skype Entreprise local vers Teams](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a>Déclaration de clôture

Microsoft Teams peut permettre à votre organisation de réunir tous les employés, travailleurs de l’information et employés en ligne, sur une seule plateforme. Vous pouvez [commencer dès aujourd’hui.](https://products.office.com/microsoft-teams/group-chat-software) Vous pouvez rester en contact avec toutes nos dernières annonces et mises à jour mensuelles de [produits ici.](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog)

Par ailleurs, étant donne lieu à la gestion de l’état actuel de COVID-19 par des entreprises du monde entier, nous avons créé une série de contenus qui vous aideront à utiliser Teams afin d’obtenir l’impact maximal que votre organisation peut avoir.

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

Teams s’appuie sur Exchange Online, SharePoint Online, OneDrive Entreprise et les groupes Microsoft 365 pour offrir à vos utilisateurs une expérience Microsoft 365 ou Office 365 entièrement intégrée. Comme indiqué ci-dessus, Teams fonctionne sans un déploiement complet de ces services, avec des fonctionnalités limitées. Vous pouvez en savoir plus sur Teams et ses conditions préalables ici : [Bienvenue dans Teams.](teams-overview.md)

Pour plus d’informations sur chacun des services répertoriés ci-dessus, suivez les liens ci-dessous :

  - Exchange Online est utilisé pour les fonctionnalités de calendrier et le stockage de messages d’égal à égal dans Teams. Pour en savoir plus, lisez [comment Exchange et Teams interagissent](exchange-teams-interact.md)

> [!IMPORTANT]
> Pour l’échange teams avec Exchange en local, vous devez configurer le nouveau protocole d’authentification OAuth Exchange, comme décrit dans la procédure Configurer l’authentification [OAuth](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)entre les organisations Exchange et Exchange Online.

  - SharePoint est utilisé pour le partage de fichiers dans les canaux, tandis que /OneDrive Entreprise est utilisé pour le partage de fichiers dans une conversation en tête-à-tête ou en groupe. Pour en savoir plus, lisez [comment SharePoint Online et OneDrive Entreprise interagissent avec Microsoft Teams.](sharepoint-onedrive-interact.md)

  - [Les groupes Microsoft 365 sont](office-365-groups.md) utilisés pour la création/gestion d’équipes et de canaux.


## <a name="related-topics"></a>Rubriques connexes

[Illustrations architecture IT Microsoft Teams et solutions téléphonie](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[Planifier la connectivité hybride entre Skype Entreprise Server et Office 365](/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[Prise en charge des travailleurs à distance à l’aide de Teams](support-remote-work-with-teams.md)

[Travailler à distance avec Microsoft 365](https://aka.ms/remote-work)