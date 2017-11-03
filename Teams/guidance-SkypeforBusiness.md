---
title: "Activer Microsoft Teams côte à côte avec Skype Entreprise"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Guide d’utilisation de Skype Entreprise et Microsoft Teams côte à côte"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: b1a635fe4abb607064a0e26240ed58715fa43a8d
ms.sourcegitcommit: 8cc7856bb7c305e0e96a4178535b1570cbfc3694
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/28/2017
---
<a name="enable-microsoft-teams-side-by-side-with-skype-for-business"></a>Activer Microsoft Teams côte à côte avec Skype Entreprise 
=============================================================

Pour les organisations ayant déployé Skype Entreprise Online, le lancement récent de Microsoft Teams offre la possibilité d’évaluer le potentiel de Teams comme solution unique de communication et de collaboration, ainsi que les différences entre les deux solutions et comment elles peuvent coexister dans votre environnement.

Si Teams peut répondre à vos besoins actuellement, vous pouvez commencer à l’adopter comme solution unique de communication et de collaboration pour votre organisation.

Teams est activée par défaut, sur tous les clients éligibles. Vous devez donc décider de la manière de gérer Teams cote à côte avec Skype Entreprise et continuer à répondre aux attentes des utilisateurs.

De manière générale, il existe deux parcours du client côte à côte principaux. Ce sont les suivants :

-   **Option 1 :** parcours du client côte à côte non géré.

    Le service informatique ne contrôle pas activement l’expérience côte à côte, et les utilisateurs ont la possibilité de choisir leur application favorite.

-   **Option 2 :** parcours du client côte à côte géré.

    Le service informatique contrôle l’expérience côte à côte, et présente Teams aux utilisateurs progressivement en leur présentant d’abord un nouvel espace de travail en collaboration basé sur la conversation avec des expériences de conversation privée puis de réunion, et enfin les expériences d’appels dans Teams.

![Diagramme de deux parcours du client côte-à-côte : Géré et non géré.](media/guidance_SkypeforBusiness_image1.png)

<a name="side-by-side-benefits-and-considerations"></a>Avantages et inconvénients de l’expérience côte à côte
----------------------------------------

Chaque parcours présente des avantages et des inconvénients à évaluer pour déterminer la bonne direction en fonction du profil de votre organisation. Le tableau ci-dessous compare les parcours du client côte à côte géré et non géré.


<table>
<thead>
<tr class="header">
<th align="left">Chemins de migration</th>
<th align="left">Côte à côte non géré</th>
<th align="left">Côte à côte géré</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong>Profil de l’organisation</strong></td>
<td align="left"><ul>
<li>Généralement les organisations plus petites sans ressources informatiques dédiées</li>
<li>Le service informatique laisse les utilisateurs sélectionner les outils appropriés pour leur travail</li>
<li>Skype Entreprise utilisé principalement pour la messagerie instantanée et les réunions</li>
</ul></td>
<td align="left"><ul><li>Généralement, les moyennes et grandes organisations</li>
<li>Le service informatique souhaite contrôler le lancement des nouveaux outils plus rigoureusement</li>
<li>Adoption plus grande de Skype Entreprise actuellement</li>
<li>Complexité accrue au niveau du réseau et de l'infrastructure</li>
<li>Plusieurs emplacements</p>
<li>Préférence pour une application unique avec des fonctionnalités de communications unifiées uniques</li></ul></td>
</tr>
<tr class="even">
<td align="left"><strong>Avantages</strong></td>
<td align="left"><ul>
<li>Permet d’utiliser des fonctionnalités dans Teams qui ne sont pas disponibles dans Skype Entreprise</li>
<li>Espace de travail plus moderne dans Office 365</li>
<li>Plus de flexibilité pour les utilisateurs</li>
<li>Permet d’utiliser toutes les fonctionnalités simultanément</li>
</ul></td>
<td align="left"><ul><li>Permet d’utiliser des fonctionnalités dans Teams qui ne sont pas disponibles dans Skype Entreprise</li>
<li>Espace de travail plus moderne dans Office 365</li>
<li>Réduit l’impact sur la productivité des utilisateurs</li>
<li>Réduit la superposition des fonctionnalités</li>
<li>Rationalise le choix des outils pour les scénarios de communications unifiées</li>
<li>Permet au service informatique et à l’entreprise d’activer les fonctionnalités en fonction des besoins de l’organisation</li>
<li>Contrôle le rythme des changements pour les utilisateurs</li></ul></td>
</tr>
<tr class="odd">
<td align="left"><strong>Inconvénients</strong></td>
<td align="left"><ul>
<li>Plusieurs applications avec des fonctionnalités similaires qui se superposent</li>
<li>Plus de possibilités de confusion de la part des utilisateurs, ce qui peut entraîner plus d’appels de l’assistance, de l'informatique fantôme et avoir un impact sur la productivité</li>
<li>La planification et la supervision du réseau doivent prendre en compte deux services</li>
<li>Travail de gestion des changements accru et immédiat : sensibilisation, formation et support</li>
<li>Les utilisateurs peuvent rencontrer des limitations de l'interopérabilité entre les applications</li>
</ul></td>
<td align="left"><ul><li>Le service a un contrôle précis, des licences aux expériences des utilisateurs, ce qui nécessite des cycles de planification et d’implémentation supplémentaires</li>
<li>Formation des utilisateurs et action requises pour désactiver les fonctionnalités sélectionnées dans Teams</li>
<li>Travail de gestion des changements requis pour désactiver les fonctionnalités sélectionnées dans Teams</li>
<li>La planification et la supervision du réseau doivent prendre en compte deux services</li>
<li>Les utilisateurs peuvent rencontrer des limitations de l'interopérabilité entre les applications</li></ul></td>
</tr>
</tbody>
</table>


<a name="unmanaged-side-by-side-customer-journey"></a>Parcours du client côte à côte non géré
---------------------------------------


![Diagramme de parcours du client côte à côte non géré.](media/guidance_SkypeforBusiness_image4.png)

Dans un parcours du client côte à côte non géré, Teams est présenté comme solution de collaboration (espace de travail basé sur les conversations, canaux, applications, intégration avec les autres charges de travail Office 365, etc.) qui implique un logiciel client et un client Web sur les ordinateurs de bureau (PC ou Mac) et les appareils mobiles.


Par défaut, Teams présente également des fonctionnalités qui se superposent avec Skype Entreprise, incluant la conversation et les appels privés, ainsi que les réunions planifiées. Cela signifie que Teams fournit des fonctions de communication et de collaboration complètes à l’organisation, tandis que Skype Entreprise fournit en même temps des fonctionnalités similaires.

Teams prend en charge l’interopérabilité avec les utilisateurs de Skype Entreprise Online, et les utilisateurs ont la possibilité de choisir leur application de conversation et d’appels favorite lorsqu'ils lancent Teams. Si un utilisateur choisit Teams comme application favorite, et qu'un autre utilisateur n’a pas installé Teams ou a choisi Skype Entreprise comme application de conversation et d’appels favorite, ils peuvent continuer à discuter et s’appeler par le biais des fonctionnalités d’interopérabilité intégrées dans Teams.

Microsoft améliore en permanence les expériences d’interopérabilité. Au début, il a pu arriver que les expériences d'interopérabilité ne répondent pas aux attentes des utilisateurs. Skype Entreprise restant disponible pour les utilisateurs, ils peuvent basculer sur Skype Entreprise pour les fonctionnalités qui ne peuvent pas être fournies actuellement par Teams.

Les réunions planifiées dans Teams sont une autre fonctionnalité qui se superpose permettant aux utilisateurs de planifier des réunions Teams ou Skype Entreprise. Chaque application a ses propres avantages et au fil du temps, lorsque l’expérience de réunion répondra aux besoins de l’entreprise ou dépassera les fonctionnalités de Skype Entreprise pour les réunions, les utilisateurs devraient basculer naturellement sur les réunions Teams.

Dans ce parcours du client côte à côte non géré, préparez votre équipe de support technique à gérer les appels de support des utilisateurs lorsqu'ils rencontrent des problèmes avec les fonctionnalités d’interopérabilité. Ou bien, conseillez aux utilisateurs de choisir les réunions Teams au lieu des réunions Skype Entreprise, et vice-versa.

Ce parcours du client côte à côte peut s’appliquer à votre organisation, les utilisateurs étant plus réceptifs à la nature de l’expérience côte à côte non gérée, et l’organisation permettant ouvertement aux utilisateurs de choisir les outils de communication et de collaboration qui répondent le mieux à leurs besoins.

<a name="managed-side-by-side-customer-journey"></a>Parcours du client côte à côte géré
-------------------------------------

![Diagramme de parcours du client côte à côte géré.](media/guidance_SkypeforBusiness_image2.png)

Un parcours du client côte à côte géré est la solution si l’organisation souhaite avoir plus de contrôle sur la manière dont Teams est introduit.

-   La **première étape** de ce parcours est une phase pilote limitée de Teams axée sur les besoins de collaboration modernes (espace de travail basé sur les conversations, canaux, applications, intégration avec les autres charges de travail Office 365, etc.). Les réunions de canal et les conversations privées ponctuelles dans Teams sont également activées pour permettre aux utilisateurs pilotes d’évaluer l’expérience de réunions et les expériences de conversation privée de Teams. À ce stade, les fonctionnalités de réunions planifiées et d’appels privés sont désactivées. Pour démarrer une phase pilote, accédez à la rubrique [Équipes pilotes avec Skype Entreprise](pilot-essentials.md).
    
-   La **seconde étape** de ce parcours consiste à étendre le lancement de Teams pour la collaboration moderne avec la conversation privée dans toute l’organisation. Les réunions planifiées et les appels privés restent désactivés dans Teams pour limiter la superposition avec les fonctionnalités de Skype Entreprise.

    À ce stade, vous pouvez déterminer si l’application de conversation favorite doit être définie sur Teams ou Skype Entreprise pour l’ensemble de l’organisation.

    - Si vous définissez Teams, préparez vos utilisateurs à gérer les problèmes d’interopérabilité initiaux lorsqu’ils communiquent avec les autres parties au sein et au-delà de l’organisation.
    
    - Si vous définissez Skype Entreprise, les conversations privées au sein de Teams restent dans Teams, et les utilisateurs finaux peuvent bénéficier immédiatement de la nature permanente multiplateforme des fonctionnalités de conversation au sein de Teams, et continueront à utiliser Skype Entreprise pour les conversations privées avec les utilisateurs de Skype Entreprise, au sein et au-delà de l’organisation.


<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p>Remarque</p></td>
<td align="left"><br><br>Le paramètre d’application de conversation favorite n’est disponible actuellement qu’au niveau du client. Une formation des utilisateurs et une campagne d’adoption seront nécessaires pour effectuer la configuration à l’échelle de l’organisation prévue.</td>
</tr>
</thead>
<tbody>
</tbody>
</table>

La **troisième étape** du parcours du client côte à côte géré commence lorsque l’organisation décide que l’expérience de réunion et les fonctionnalités de Teams répondent à ses besoins. En activant les réunions privées et de canal dans Teams, des options permettant de planifier des réunions Teams et des réunions Skype Entreprise sont présentées aux utilisateurs. Les utilisateurs devraient donc basculer naturellement sur les réunions Teams étant donné les innovations permanentes introduites dans Teams. Pour amener les utilisateurs à passer de l’utilisation de Skype Entreprise à celle de Teams, implémentez un programme de gestion des changements solide incluant une formation, un support et des communications expliquant la valeur ajoutée de Teams, avec des orientations claires sur la prise en main de Teams. Utilisez nos ressources de [Préparation des utilisateurs](http://aka.ms/UserReadiness) pour vous aider à concevoir une campagne de sensibilisation.


La **quatrième étape** du parcours du client côte à côte géré commence par l’activation des appels dans Teams. Les fonctionnalités d'interopérabilité de Teams seront privilégiées dans cette étape pour assurer une expérience côte à côte transparente. Dans l’idéal, pour imposer l’utilisation de Teams pour les appels privés, Teams est défini comme application d’appels par défaut. 

Au fil du temps, l’ensemble de l’organisation peut théoriquement s’appuyer uniquement sur Teams pour répondre aux besoins de communication et de collaboration et passer à la **cinquième étape**. Pour savoir quand de nouvelles fonctionnalités seront disponibles dans Teams, reportez-vous à la [Feuille de route Office 365](http://aka.ms/TeamsRoadmap). 

<a name="managing-side-by-side-experience"></a>Gestion de l’expérience côte à côte
--------------------------------

Par défaut, pour les organisations disposant d’abonnements Office 365 éligibles, Microsoft Teams est activée. Si votre organisation répond aux critères pour le parcours du client côte à côte non géré, nous vous recommandons vivement de conserver ce paramètre tel quel pour favoriser l’adoption systématique de Microsoft Teams.

Teams est accessible par le biais de clients de bureau avec un navigateur Web moderne ne nécessitant pas de droits d’administrateur informatique (pour l'installation, s’applique uniquement aux PC actuellement) et de clients mobiles.

Toutes les fonctionnalités dans Teams, de la conversation privée aux appels, aux réunions ponctuelles et planifiées et aux applications sont activées par défaut, ce qui permet aux utilisateurs d’expérimenter et d’utiliser les fonctionnalités qui répondent à leurs besoins. Une expérience de première utilisation dans Teams guide les utilisateurs dans le choix de leur application de conversation et d’appels favorite (Microsoft Teams ou Skype Entreprise).

Si votre organisation requiert une version plus contrôlée des nouveaux outils comme Teams, les options suivantes peuvent être envisagées pour votre parcours du client côte à côte géré :

-   Phase pilote et lancement de Teams pour la collaboration. Consultez la rubrique [Équipes pilotes avec Skype Entreprise](pilot-essentials.md).

-   Lancement de Teams pour les réunions

-   Lancement de Teams pour les appels

### <a name="teams-pilot-and-rollout-for-collaboration"></a>Phase pilote et lancement de Teams pour la collaboration

Microsoft Teams a été conçu essentiellement autour de la conversation permanente et l’intégration avec Office 365 en améliorant les groupes Office 365.

Étant donné que, par défaut, Teams est activé pour les utilisateurs dans votre organisation disposant d'une licence d’abonnement à Office 365 éligible, la version pilote de Teams impliquera de désactiver la licence Teams de tous les utilisateurs qui ne font pas partie du groupe pilote.

Pour orienter la solution de collaboration et de conversation privée sur la version de Teams, et pour réduire la confusion des utilisateurs due aux fonctionnalités qui se superposent avec Skype Entreprise, vous pouvez modifier les paramètres suivants au niveau du client Office 365. Pour modifier ces paramètres Office 365, consultez la rubrique [Configurer Microsoft Teams dans votre organisation Office 365](Office-365-set-up.md).

<table>
<thead>
<tr class="header">
<th align="left">Section</th>
<th align="left">Paramètre</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong><br>Appels et réunions</strong></td>
<td align="left"><p>Autoriser la planification de réunions privées : <strong>désactivé</strong></p><p>Autoriser la planification de réunions de canal : <strong>désactivé</strong></p><p>Autoriser les appels privés : <strong>désactivé</strong></p></td>
<td align="left"><p>Désactiver ce paramètre empêche les utilisateurs de planifier des réunions privées</p><p>Désactiver ce paramètre empêche les utilisateurs de planifier des réunions de canal</p><p>Désactiver ce paramètre empêche les utilisateurs de passer des appels privés (audio et vidéo)</p></td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p>Remarque</p></td>
<td align="left"><br><br>Vous devez désactiver les appels privés pour les utilisateurs professionnels et de l’entreprise, et les utilisateurs invités (si l’accès invité s’applique à votre organisation).</td>
</tr>
</thead>
<tbody>
</tbody>
</table>



Avec cette configuration, la manière dont les réunions fonctionnent dans Teams peut être présentée aux utilisateurs en préconisant l’utilisation de la réunion ponctuelle, qui permet d’utiliser les fonctions audio, vidéo et le partage d’écran dans le cadre de l’expérience de collaboration moderne. Les utilisateurs finaux peuvent également bénéficier des fonctionnalités de conversation privée permanente et multiplateforme.

Une phase pilote réussie de Teams pour la collaboration et la conversation privée peut être suivie d'un lancement dans l’ensemble de l’organisation en activant la licence Teams pour tous les utilisateurs.

<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p>Remarque</p></td>
<td align="left">Pendant la phase pilote, et pendant la phase deux lorsque la conversation privée est activée, un utilisateur de Teams qui discute avec un utilisateur de Skype Entreprise ne pourra pas effectuer les opérations suivantes :<br>
- Lancer un appel vidéo à partir d'une session de conversation<br>
- Transférer des fichiers <br>
- Lancer un appel de groupe à partir de la session de conversation<br>
- Les utilisateurs ne pourront pas démarrer une session de partage de bureau<br>

</td>
</tr>
</thead>
<tbody>
</tbody>
</table>


### <a name="rollout-of-teams-for-meetings"></a>Lancement de Teams pour les réunions

Lorsque les utilisateurs sont habitués à collaborer en utilisant Microsoft Teams, les réunions planifiées peuvent être envisagées comme prochaine fonctionnalité à activer dans l’organisation.

<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p>Remarque</p></td>
<td align="left"><br><br>Les personnes qui organisent des réunions planifiées doivent leurs boîtes aux lettres dans Exchange Online mutualisées (ou vNext Exchange Online dédié).</td>
</tr>
</thead>
<tbody>
</tbody>
</table>

Les paramètres suivants peuvent être configurés au niveau du client pour activer les réunions planifiées dans Teams, et les paramètres s’appliquent uniquement aux utilisateurs professionnels et de l’entreprise uniquement.

<table>
<thead>
<tr class="header">
<th align="left">Section</th>
<th align="left">Paramètre</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong><br>Appels et réunions</strong></td>
<td align="left"><p>Autoriser la planification de réunions privées : <strong>activé</strong></p><p>Autoriser la planification de réunions de canal : <strong>activé</strong></p></td>
<td align="left"><p>Activer ce paramètre permet aux utilisateurs de planifier des réunions privées</p><p>Activer ce paramètre permet aux utilisateurs de planifier des réunions de canal</p></td>
</tr>
</tbody>
</table>


Les réunions planifiées peuvent être organisées par le biais du client de bureau Teams, d’un navigateur ou de Microsoft Outlook en utilisant le complément Réunion pour Microsoft Teams. Une fois les réunions planifiées activées dans Teams, nous recommandons de commencer à former les utilisateurs à la création de nouvelles réunions Teams ou de mettre à jour les réunions Skype Entreprise sur les réunions Teams.

### <a name="rollout-of-teams-for-calling"></a>Lancement de Teams pour les appels

La fonctionnalité d’appels privés de Teams sera développée en permanence, et fournira au fil du temps un remplacement attrayant de Skype Entreprise. Lorsque votre organisation estime que les fonctionnalités d’appels privés de Teams répondent à ses besoins, les paramètres suivants peuvent être configurés au niveau du client pour activer les appels privés dans Teams. 

<table>
<thead>
<tr class="header">
<th align="left">Section</th>
<th align="left">Paramètre</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong><br>Appels et réunions</strong></td>
<td align="left"><p>Autoriser les appels privés : <strong>activé</strong></p></td>
<td align="left"><p>Activer ce paramètre permet aux utilisateurs de passer des appels privés (audio et vidéo)</p></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p>Remarque</p></td>
<td align="left"><br><br>Autoriser les utilisateurs à discuter en privé : lorsque ce paramètre est activé, les utilisateurs peuvent discuter en privé avec les autres utilisateurs.</td>
</tr>
</thead>
<tbody>
</tbody>
</table>


À cette étape, il doit être demandé à tous les utilisateurs de choisir Teams comme application d’appels favorite.

Avec l’activation des appels privés, Teams offrira toutes les fonctionnalités fournies actuellement par Skype Entreprise, et les utilisateurs peuvent commencer à utiliser Teams pour répondre à leurs besoins en matière de communication et de collaboration.


<table>
<thead>
<tr class="header">
<td align="left"><p><img src="media/pilot_essentials_image2.png" /></p></td>
<td align="left">
<p><strong>Action suivante :</strong> lorsque Teams est opérationnelle côte à côte avec Skype Entreprise, [générez une valeur ajoutée en incitant les utilisateurs à adopter Teams](continue-journey.md), en continuant votre parcours de remplacement de Skype Entreprise par Teams.</td>
</tr>
</thead>
<tbody>
</tbody>
</table>