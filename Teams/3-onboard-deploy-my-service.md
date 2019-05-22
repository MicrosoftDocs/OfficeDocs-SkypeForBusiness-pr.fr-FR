---
title: Déployer le service vocal cloud de Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 05/16/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Téléchargez le manuel d’utilisation du site pour planifier le déploiement de vos équipes et accélérer et optimiser l’adoption des utilisateurs, la perception de la qualité et la satisfaction.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 90f49b3da1aec6d5f81f43674db5bc8cdb3822aa
ms.sourcegitcommit: 30995da65ff6a9b33534c3818833cf0ae1952ab9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/22/2019
ms.locfileid: "34344700"
---
# <a name="deploy-my-service"></a>Déployer mon service

Cet article fournit une vue d’ensemble de la configuration requise pour le déploiement approprié des services vocaux Cloud. En suivant les recommandations en matière de déploiement de services vocaux Cloud, vous pouvez vous assurer que vous disposez bien de toutes les exigences et que vous fournissez des résultats répétitifs.

## <a name="site-enablement-playbook-for-microsoft-teams-voice-workloads"></a>Manuel d’activation des sites pour les charges de travail Microsoft teams

Utilisez ce manuel pour aider votre organisation à planifier et à exécuter correctement le déploiement des fonctionnalités vocales de Microsoft teams sur une base site par site.

Incluant toutes les activités requises, les chronologies recommandées et les liens vers des instructions correspondantes pour chaque activité, le présent manuel décrit les conseils de bout en bout pour vous permettre de garantir le déploiement de votre voix teams pour un site donné, en insistant sur les facteurs importants. à l’utilisateur.

En remplissant les activités de ce manuel, votre organisation peut:

-   Planifiez et planifiez efficacement le déploiement de votre équipe.

-   Accélérez et optimisez l’adoption des utilisateurs.

-   Réduisez les besoins en matière de support et augmentez la satisfaction des utilisateurs.

> [!NOTE]
> Cet article et le manuel associé n’ont pas été prévus pour décrire chaque étape de configuration technique requise pour l’activation du service ou la fourniture de tonalités de numérotation à un site spécifique. Au lieu de cela, ils se concentrent sur les activités et les tâches qui sont recommandées pour intégrer facilement les utilisateurs et leur permettre d’utiliser les charges de travail vocales d’équipes grâce à une transition rapide et plus fluide, tout en minimisant le niveau de prise en charge requise. Pour obtenir des conseils techniques sur la configuration de votre environnement pour teams Voice, voir les listes de vérification d’intégration pour la [Configuration des charges de travail vocales](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)d’équipe, [configuration du routage direct dans teams](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md), fonctionnalités de [base](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)d’équipes, [réseau pour teams](onboarding-checklist-configure-networking.md)et [activation d’Office 365](onboarding-checklist-enable-office-365.md).

<!--ENDOFSECTION-->

## <a name="playbook-focus-areas"></a>Zones ciblées du manuel

Le manifeste consiste à traiter les facteurs qui influencent la perception de l’utilisateur par un déploiement vocal d’équipes. Les activités et les tâches sont regroupées dans les zones ciblées suivantes:

-   Validation de la disponibilité du service
    - Audioconférence,
    - Offres d'appels
    - Routage direct

-   Activation utilisateur

-   Points de terminaison

-   Utilisation et qualité

-   Croissante

Le manuel [d’activation des sites pour les appels vocaux](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) est un classeur Microsoft Excel. Chacun de ces cinq domaines de focalisation est une feuille séparée dans le classeur, et chaque tâche et activité de déploiement est regroupée sur l’une de ces feuilles.

![Capture d’écran du manuel] (media/deploy-my-service-image1.png "Capture d’écran du manuel")

> [!NOTE]
> Vous allez créer une instance distincte du manuel pour chaque site dans le cadre de votre déploiement d’équipes.

<!--ENDOFSECTION-->

## <a name="how-to-use-the-playbook"></a>Utiliser le manuel

Quelle que soit la taille et la complexité de l’emplacement, l’activation de chaque site exige de planifier vos tâches et vos activités au plus vite, et de les exécuter dans un ordre optimal, avant, pendant et après le déploiement réel du service. Nous vous recommandons de suivre ces étapes lors de la planification et de l’exécution de votre propre voyage dans Microsoft teams Voice.

1. Téléchargez le [Manuel d’activation de site pour les appels vocaux (manuel)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) pour Microsoft teams Voice.

2. Créez une copie distincte du manuel pour chaque site.

3. Dans l’onglet de la feuille de passe du **{nom_site-code}**, remplacez **{SiteName-code}** par le nom de site et/ou le code du site pertinents.

4. Entrez le **nom du site, le code du site**et la **Date de lancement prévue**, comme illustré ci-dessous. Il s’agit d’une étape essentielle, car elle ajuste les délais recommandés pour chaque activité du manuel.

   ![Exemple avec le nom du site, le code du site et la date de lancement planifiée] (media/deploy-my-service-image2.png "Exemple avec le nom de site New York, le code de site NY01 et la date de début planifiée 20-Mar-18")

5. Examinez chaque activité, effectuez les actions nécessaires et mettez à jour l’État à mesure que vous parcourez la chronologie. Le statut est représenté sous forme graphique, comme décrit ci-dessous:
  
   - ![Illustration d’une coche](media/deploy-my-service-image3.png) verte **: oui ou non applicable (vert):** l’activité est terminée ou n’est pas applicable pour ce site, et aucune action supplémentaire n’est requise.</li>
    - ![Image d’un point](media/deploy-my-service-image4.png) d’exclamation jaune <strong>l’activité n’est pas achevée (jaune):</strong> l’activité n’a pas encore été achevée et doit être mise à jour sur Oui ou non.</li>
   - ![Illustration d’un X](media/deploy-my-service-image5.png) rouge <strong>(rouge):</strong> l’activité ne peut pas être effectuée en raison d’un problème et doit être acheminée vers la réunion d’État du projet.</li></ul>

6. Le statut est répété dans chaque section, et le titre de section est mis en forme avec l’un de ces indicateurs d’État. Le **statut hebdomadaire** est également mis à jour automatiquement.

![Capture d’écran des déploiements de l’état hebdomadaire dans le manuel] (media/deploy-my-service-image6.png "Capture d’écran des déploiements de l’état hebdomadaire dans le manuel")

> [!TIP]
> Répétez les étapes ci-dessus pour tous les emplacements que vous avez.

> [!IMPORTANT]
> Certaines étapes peuvent ne pas être applicables à tous les sites et emplacements. Si une activité spécifique n’est pas pertinente pour un site, vous devez sélectionner **non applicable** pour cette activité. **Ne supprimez pas** les lignes du manuel. dans le cas contraire, les formules de report ne fonctionnent pas.<br/><br/>
Soyez attentif aux activités qui peuvent durer plus longtemps que prévu (par exemple, le transfert de numéros et les activités d’approvisionnement). Ces activités peuvent avoir un impact négatif sur la chronologie du déploiement de site. Veillez à vérifier et à mettre à jour la liste des activités et la chronologie associée de manière hebdomadaire, et à les présenter à des [réunions du Comité de direction](https://docs.microsoft.com/MicrosoftTeams/envision-steering-committee-complete-guide) pour vous assurer que les parties prenantes sont consciente de l’état de chaque site et des écarts possibles de la planification du déploiement.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="Icon depicting decision points"/> <br/>Points de décision</td><td><ul><li>Déterminez si le manuel d’activation du site est requis pour votre déploiement.</li><li>Déterminez qui sera responsable de la personnalisation du manuel d’activation des sites de Microsoft teams pour chaque site que vous déploierez.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="Icon depicting the next steps"/><br/>Étapes suivantes</td><td><ul><li><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">Télécharger le manuel d’activation de site</a>.</li><li>Personnalisez le manuel d’activation de site pour votre premier site.</li><li>Répétez cette procédure si nécessaire pour les sites supplémentaires.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->