---
title: Déploiement de service vocal de cloud Microsoft Teams
author: rmw2890
ms.author: MyAdvisor
manager: lehewe
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Téléchargez le manuel d’activation de Site pour planifier votre déploiement d’équipes et d’accélérer et d’optimiser l’adoption par les utilisateurs, la perception de la qualité et de satisfaction.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: f59b7568f5ec0d3d9b6ef3b04f4094b222d0702b
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/05/2018
---
# <a name="deploy-my-service"></a>Déployer mon service

Cet article donne une vue d’ensemble de la configuration requise pour le déploiement des services en nuage voix correctement. En suivant les conseils pour le déploiement de services de téléphonie de nuage, vous pouvez vous assurer vous avec succès toutes les exigences de compte et fournir des résultats répétables.

## <a name="site-enablement-playbook-for-microsoft-teams-voice-workloads"></a>Manuel de prise en charge de site pour les charges de travail Teams de Microsoft voice

Ce manuel permet d’aider votre entreprise à planifier et exécuter le déploiement de fonctionnalités vocales de Microsoft Teams sur une base site par site.

Y compris toutes les activités, recommandé de chronologies et des liens correspondants de recommandations pour chaque activité, ce manuel traite des conseils de bout en bout pour garantir un déploiement réussi de voix équipes pour un site donné, en mettant l’accent sur des facteurs qui sont importants pour l’utilisateur.

En effectuant les activités dans ce manuel, votre entreprise peut :

-   Planifier et planifier le déploiement de vos équipes de manière efficace.

-   Accélérez et optimisez l’adoption par les utilisateurs.

-   Réduire les besoins en support et accroître la satisfaction de l’utilisateur.

> [!NOTE]
> Cet article et le manuel associé ne sont pas destinés à décrire chaque étape de la configuration technique requise pour l’activation des services ou fourniture de tonalité à un site spécifique. À la place, ils se concentrent sur les activités et tâches recommandés aux utilisateurs intégrés facilement et les commence à consommer des charges de travail aux équipes voix via une transition rapide et sans heurts avec un fort engouement, tout en réduisant les exigences en matière de prise en charge. Pour des conseils sur la meilleure façon de configurer votre environnement pour la voix d’équipes techniques, reportez-vous à l’intégration des listes de contrôle pour la [Configuration des charges de travail aux équipes voice](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams), [les fonctionnalités de base aux équipes](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-microsoft-teams-core-capabilities), [mise en réseau pour les équipes](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-networking)et [l’activation d’Office 365 ](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-enable-office-365).

<!--ENDOFSECTION-->

## <a name="playbook-focus-areas"></a>Domaines manuel

Le manuel vise à relever les facteurs qui influencent la perception de l’utilisateur d’un déploiement de voix d’équipes. Les tâches et les activités sont regroupées dans les domaines suivants :

-   Validation de la disponibilité du service

-   Activation de l’utilisateur

-   Points de terminaison

-   L’utilisation et la qualité

-   Adoption

Le [Manuel d’activation de Site pour la voix (manuel)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) est un classeur Microsoft Excel. Chacun de ces cinq domaines est une feuille distincte dans le classeur, et chaque tâche de déploiement et les activités sont regroupées sur l’une de ces feuilles.

![Capture d’écran du manuel] (media/deploy-my-service-image1.png "Capture d’écran du manuel")

> [!NOTE]
> Vous allez créer une instance distincte de la manuel pour chaque site dans la portée de votre déploiement d’équipes.

<!--ENDOFSECTION-->

## <a name="how-to-use-the-playbook"></a>Comment utiliser le manuel

Quelle que soit la taille et la complexité de l’emplacement, l’activation de chaque site nécessite que vous planifiez vos tâches et vos activités suffisamment tôt et de les exécuter dans l’ordre optimal : avant, pendant et après le déploiement du service proprement dit. Nous vous recommandons de suivre ces étapes de planifier et d’exécuter votre propre parcours à voix de Teams de Microsoft.

1.  Téléchargez le [manuel d’activation de Site pour la voix (manuel)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) pour les équipes Microsoft Voice.

2.  Créer une copie distincte de la manuel pour chaque site.

3.  Sous l’onglet de la feuille intitulée **manuel pour le Code {SiteName}**, remplacez **{Nom de site-Code}** avec le nom du site approprié et/ou le code de site.

4.  Entrez le **nom du Site, code de Site**et la **date de lancement prévue**, comme illustré ci-dessous. Il s’agit d’une étape essentielle, car elle ajuste les délais recommandés pour chaque activité dans le manuel.

    ![Exemple de nom de site de New York, NY01, le code de site et date de lancement prévue de 20-Mar-18] (media/deploy-my-service-image2.png "Exemple de nom de site de New York, NY01, le code de site et date de lancement prévue de 20-Mar-18")

5.  Passez en revue chaque activité, prennent les mesures nécessaires et mettre à jour le statut que vous passez en revue le scénario. État est représenté graphiquement, comme décrit ci-dessous :
    <ul>
    <li>![Coche verte](media/deploy-my-service-image3.png) **Oui ou non applicable (vert) :** l’activité a été achevée, ou il n’est pas applicable à ce site, et aucune action supplémentaire n’est nécessaire.</li>
    <li>![Point d’exclamation jaune](media/deploy-my-service-image4.png) **l’activité n’est pas achevée encore (jaune) :** l’activité n’a pas encore terminée et il doit être mis à jour à Oui ou non selon sa planification.</li>
    <li>![Rouge X](media/deploy-my-service-image5.png) **Aucun (rouge) :** l’activité ne peut pas être terminée en raison d’un problème et doit être exécutée à la réunion.</li></ul>

6.  Le statut est reporté dans chaque section, et l’en-tête de section est mis en forme avec l’un de ces indicateurs d’état. **Rapport hebdomadaire** est également mis à jour automatiquement.

![Capture d’écran du hebdomadaire état roll-ups dans le manuel] (media/deploy-my-service-image6.png "Capture d’écran du hebdomadaire état roll-ups dans le manuel")

> [!TIP]
> Répétez les étapes ci-dessus pour tous les emplacements que vous avez.


> [!IMPORTANT]
> Certaines étapes n’est peut-être pas applicables à tous les sites et emplacements. Si une activité donnée ne correspond pas à un site, vous devez sélectionner **non applicable** pour cette activité. **Ne supprimez pas** les lignes dans le manuel ; Dans ce cas, les formules de cumul d’état ne fonctionnent pas.<br/><br/>
Faites attention aux activités qui peuvent prendre plus de temps que vous prévues, telles que le portage des numéros et des activités d’approvisionnement. Ces activités peuvent une incidence négative sur la barre de planning de déploiement de site. Veillez à passer en revue et mettre à jour la liste des activités et la chronologie associée toutes les semaines, les présenter aux [réunions du comité de direction](https://docs.microsoft.com/MicrosoftTeams/envision-steering-committee-complete-guide) pour vous assurer que les parties prenantes sont informés de l’état de chaque site et tous les écarts possibles à partir de la planification du déploiement.


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Points de décision</td><td><ul><li>Décider si le manuel de prise en charge du Site est nécessaire pour votre déploiement.</li><li>Déterminer qui sera responsable de la personnalisation de la manuel d’activation de Site pour le Teams de Microsoft pour tous les sites que vous allez déployer.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Étapes suivantes</td><td><ul><li>Téléchargez le manuel de prise en charge du Site.</li><li>Personnaliser le manuel de gestion de Site pour votre site premier.</li><li>Répétez si nécessaire pour les sites supplémentaires.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->