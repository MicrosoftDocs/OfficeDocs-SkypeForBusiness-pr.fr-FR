---
title: Déployer le service vocal cloud de Microsoft Teams
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 05/16/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Télécharger le manuel activation de Site pour planifier votre déploiement équipes et accélérer et optimiser l’adoption de l’utilisateur, perception de la qualité et de satisfaction.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8ea80d3ba87a6499cba3bf52b5f70d45d0619c8a
ms.sourcegitcommit: bc2b227b4ac0a9521993f808a1361b4f9bc7faad
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/14/2019
ms.locfileid: "30568463"
---
# <a name="deploy-my-service"></a>Déployer mon service

Cet article donne une vue d’ensemble de la configuration requise pour le déploiement correctement les services en nuage voix. En suivant les instructions pour le déploiement de services en nuage voice, vous pouvez vous assurer que vous correctement toutes les exigences de compte et fournir des résultats reproductibles.

## <a name="site-enablement-playbook-for-microsoft-teams-voice-workloads"></a>Lecture activation de site pour les charges de travail Microsoft Teams vocale

Utilisez ce manuel pour aider votre organisation à planifier et exécuter le déploiement des fonctionnalités vocales de Microsoft Teams sur une base site par site.

Y compris toutes les activités, recommandé chronologies et des liens d’instructions correspondantes pour chaque activité, ce manuel traite des conseils de bout en bout pour garantir un déploiement de voix équipes pour un site donné, en mettant l’accent sur les facteurs qui sont importantes à l’utilisateur.

En effectuant les activités dans ce manuel, votre organisation peut :

-   Planifier et planifier votre déploiement équipes efficacement.

-   Accélérer et optimiser l’adoption de l’utilisateur.

-   Réduire les besoins en matière de prise en charge et augmenter la satisfaction des utilisateurs.

> [!NOTE]
> Cet article et la lecture associé ne sont pas destinés à décrivent chaque étape de configuration technique requise pour l’activation des services ou fournissant tonalité à un site spécifique. Au lieu de cela, ils se concentrent sur les activités et recommandés pour les utilisateurs intégrés facilement des tâches et de les commence à consommer des charges de travail voix équipes via une transition rapide et en toute transparence avec un taux élevé d’adoption, tout en réduisant les exigences de prise en charge. Pour obtenir des instructions techniques sur la meilleure façon de configurer votre environnement pour voice équipes, consultez l’aide-mémoire embarquement pour la [Configuration des charges de travail voix équipes](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md), la [configuration du routage Direct dans les équipes](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md), les [équipes les fonctionnalités de base](onboarding-checklist-configure-microsoft-teams-core-capabilities.md), [réseau pour les équipes](onboarding-checklist-configure-networking.md)et [l’activation d’Office 365](onboarding-checklist-enable-office-365.md).

<!--ENDOFSECTION-->

## <a name="playbook-focus-areas"></a>Domaines lecture

L’objectif de la lecture est de résoudre les facteurs qui influencent la perception de l’utilisateur d’un déploiement de voix équipes. Tâches et activités sont regroupés dans les domaines suivants :

-   Validation de la disponibilité du service
    - Audioconférence
    - Offres d'appels
    - Routage direct

-   Activation de l’utilisateur

-   Points de terminaison

-   L’utilisation et la qualité

-   Kit d’adoption

La [Lecture d’activation de Site pour la voix (lecture)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) est un classeur Microsoft Excel. Chacun de ces cinq domaines est une feuille distincte dans le classeur, et chaque tâche de déploiement et les activités sont regroupées sur l’une de ces feuilles.

![Capture d’écran de la lecture] (media/deploy-my-service-image1.png "Capture d’écran de la lecture")

> [!NOTE]
> Vous allez créer une instance distincte de la lecture pour chaque site dans la portée de votre déploiement d’équipes.

<!--ENDOFSECTION-->

## <a name="how-to-use-the-playbook"></a>L’utilisation de la lecture

Quelle que soit la taille et la complexité de l’emplacement, l’activation de chaque site nécessite que vous envisagez de vos tâches et des activités suffisamment tôt — et de les exécuter dans l’ordre optimal — avant, pendant et après le déploiement de service. Nous vous conseillons de suivre ces étapes lorsque vous planifiez et exécutez votre propre voyage vers voix Teams Microsoft.

1. Téléchargez la [lecture d’activation de Site pour la voix (lecture)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) pour les équipes Microsoft Voice.

2. Créez un exemplaire distinct de la lecture pour chaque site.

3. Sous l’onglet de la feuille de **lecture pour {Code SiteName}**, remplacez **{Code SiteName}** par le nom de site pertinente et/ou le code de site.

4. Entrez le **nom du Site, le code de Site**et la **date de lancement prévu**, comme illustré ci-dessous. Il s’agit d’une étape importante, car elle ajuste les délais recommandées pour toutes les activités de la lecture.

   ![Exemple avec le nom du site de New York, NY01, le code de site et date de lancement prévue de 20-Mar-18] (media/deploy-my-service-image2.png "Exemple avec le nom du site de New York, NY01, le code de site et date de lancement prévue de 20-Mar-18")

5. Passez en revue chaque activité, prenez les mesures nécessaires et mettre à jour le statut que vous passez en revue la chronologie. État est représenté sous forme graphique, comme décrit ci-dessous :
   <ul>
   <li>![Coche verte](media/deploy-my-service-image3.png) <strong>Oui ou non applicable (vert) :</strong> l’activité terminée, ou il n’est pas applicable pour ce site, et aucune action supplémentaire n’est nécessaire.</li>
   <li>![Point d’exclamation jaune](media/deploy-my-service-image4.png) <strong>l’activité n’est pas achevée encore (jaune) :</strong> l’activité n’a pas encore été terminée et doit être mis à jour à Oui ou non sur sa planification.</li>
   <li>![X rouge](media/deploy-my-service-image5.png) <strong>Aucune (rouge) :</strong> l’activité ne peut pas aboutir en raison d’un problème et doit être exécutée à la réunion.</li></ul>

6. L’état est reportée dans chaque section, et l’en-tête de section est mis en forme avec une de ces indicateurs d’état. **Hebdomadaire** est également mis à jour automatiquement.

![Capture d’écran des semaine état - Reports dans la lecture] (media/deploy-my-service-image6.png "Capture d’écran des semaine état - Reports dans la lecture")

> [!TIP]
> Répétez les étapes ci-dessus pour tous les emplacements que vous avez.

> [!IMPORTANT]
> Certaines étapes peuvent ne pas être applicables à tous les sites et les emplacements. Si une activité spécifique n’est pas pertinente pour un site, vous devez sélectionner **non applicable** pour cette activité. **Ne supprimez pas** les lignes de la lecture ; Si vous procédez ainsi, les formules de cumul d’état ne fonctionnent pas.<br/><br/>
Attention aux activités qui peuvent prendre plus de temps que vous avez planifié, telles que le numéro portage et des activités d’approvisionnement. Ces activités peuvent affecter négativement le planning de déploiement de site. Veillez à consulter et de mettre à jour la liste des activités et la chronologie associé à toutes les semaines et de les présenter aux [réunions du comité directeur](https://docs.microsoft.com/MicrosoftTeams/envision-steering-committee-complete-guide) pour s’assurer que les parties prenantes sont informés de l’état de chaque site ainsi que les écarts possibles à partir de la planification du déploiement.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Points de décision</td><td><ul><li>Déterminez si la lecture d’activation de Site est requise pour votre déploiement.</li><li>Déterminer qui sera responsable de la personnalisation de la lecture d’activation de Site pour Microsoft Teams pour chaque site que vous envisagez de déployer.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">Télécharger le manuel d’activation de Site</a>.</li><li>Personnaliser la lecture d’activation de Site pour votre site premier.</li><li>Répétez pour des sites supplémentaires.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->