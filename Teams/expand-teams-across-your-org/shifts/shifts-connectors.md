---
title: Majs connecteurs
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaku
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez les connecteurs Shifts et comment les utiliser pour connecter Shifts à votre système de gestion de la main-d’œuvre.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 930f4b7a311acc7c34e60b7916071d10349c0313
ms.sourcegitcommit: bf0071417188b33fc23e2a420187da5024d4bd40
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/20/2022
ms.locfileid: "64592889"
---
# <a name="shifts-connectors"></a>Majs connecteurs

## <a name="overview"></a>Présentation

Les connecteurs Shifts vous permettent d’intégrer Shifts, l’outil de gestion des planifications dans Microsoft Teams, à votre système WFM (Workforce Management). Après avoir configuré une connexion, vos employés de première ligne peuvent afficher et gérer en toute transparence leurs planifications dans votre système WFM à partir de Shifts.

La connexion de votre système WFM à Teams permet à votre personnel de première ligne de gérer les planifications plus efficacement et simplifie les processus quotidiens pour accroître l’engagement et la productivité. Vos employés de première ligne disposent d’un emplacement unique pour leurs besoins de planification, de communication et de collaboration pour accomplir leurs tâches, où que vous soyez, sur n’importe quel appareil.

Nous proposons des connecteurs Shifts managés et open source. Cet article vous donne une vue d’ensemble des connecteurs Shifts et de leur fonctionnement.

## <a name="how-shifts-connectors-work"></a>Fonctionnement des connecteurs Shifts

Les connecteurs synchronisent les données de planification entre votre système WFM et Shifts, en intégrant les planifications de votre organisation dans Teams. Les équipes sont l’endroit où vos employés de première ligne s’engagent pour leurs besoins en matière de planification. Votre système WFM est le système d’enregistrement pour les règles d’entreprise, la conformité et l’intelligence.

Les flux de données via le connecteur permettent de s’assurer que les planifications sont toujours à jour. Les planifications de votre système WFM sont synchronisées avec shifts. De plus, les modifications apportées aux planifications dans shifts sont synchronisées avec votre système WFM en temps réel. En tant que système d’enregistrement, toutes les règles d’entreprise sont appliquées par votre système WFM avant l’enregistrement des données dans Shifts.

## <a name="managed-shifts-connectors"></a>Connecteurs Shifts managés

Les connecteurs Shifts managés sont des connecteurs développés en collaboration avec nos partenaires. Les connecteurs managés sont hébergés et gérés par nous ou nos partenaires. Avec les connecteurs managés, seule une configuration minimale est nécessaire.

### <a name="microsoft-teams-shifts-connector-for-blue-yonder"></a>connecteur Microsoft Teams Shifts pour Blue Yonder
<a name="blue_yonder"> </a>

Le connecteur Teams Shifts pour Blue Yonder est une offre de première partie hébergée et gérée par Microsoft. Avec ce connecteur, vous pouvez intégrer Shifts à Blue Yonder Workforce Management (Blue Yonder WFM) versions 2020.3, 2021.1 ou 2021.2 pour gérer vos planifications et les tenir à jour.  

> [!NOTE]
> Si vous disposez de blue Yonder WFM version 2020.3 ou 2021.1, appliquez le correctif 2020.3.0.4 ou 2021.1.0.3. Ce correctif corrige un problème où les utilisateurs reçoivent un message d’erreur persistant dans Shifts. Il résout également un problème qui empêche les utilisateurs de mettre à jour leur disponibilité dans Shifts.

:::image type="content" source="../../media/shifts-connector-blue-yonder.png" alt-text="Capture d’écran montrant une demande d’échange dans Shifts sur un appareil mobile, une demande d’approbation dans Teams sur le bureau et une planification dans blue Yonder WFM." lightbox="../../media/shifts-connector-blue-yonder.png":::

Les responsables de première ligne peuvent :

- Publiez des décalages et des planifications dans le WFM Blue Yonder et affichez-les dans Shifts.
- Créez, gérez et attribuez des décalages ouverts dans blue Yonder WFM et affichez-les dans Shifts.
- Affectez des décalages ouverts qui ont été créés dans le WFM Blue Yonder dans Shifts.
- Créez, modifiez et supprimez un délai d’attente dans le WFM Blue Yonder et affichez-le dans Shifts.
- Affichez et approuvez les demandes de planification des travailleurs dans WFM Blue Yonder et Shifts.
- Définissez et mettez à jour la disponibilité des workers dans WFM Blue Yonder et affichez-les dans Shifts.

Les travailleurs de première ligne peuvent :

- Consultez les horaires et les horaires de leur équipe et de leur équipe dans Shifts.
- Demandez un congé, ouvrez des shifts et échangez des shifts dans Shifts.
- Définissez leur disponibilité dans Shifts.

Les actions suivantes ne sont actuellement pas prises en charge :

- Ajoutez, modifiez, supprimez, enregistrez ou publiez des décalages dans Shifts.
- Ajoutez, modifiez, supprimez, enregistrez ou publiez des congés dans Shifts.
- Ajoutez, modifiez, supprimez, enregistrez ou publiez des décalages ouverts dans Shifts.

Lorsqu’un responsable ou un travailleur de première ligne tente d’effectuer l’une de ces actions dans Shifts, il reçoit un message lui indiquant que l’action n’est pas prise en charge.

#### <a name="example-scenario"></a>Exemple de scénario

Eden, un responsable, publie une planification dans Blue Yonder WFM, qui est synchronisé avec Shifts dans Teams via le connecteur. Alex, un membre du personnel, reçoit une notification dans Teams sur son appareil mobile, et affiche son horaire et les équipes affectées.

Alex doit prendre un peu de congé et demande un jour de congé à l’aide de Shifts. La demande est envoyée à Blue Yonder WFM via le connecteur en temps réel. Blue Yonder WFM garantit que la demande est conforme aux règles d’entreprise et que la demande est créée. Eden voit et approuve la demande dans blue Yonder WFM, et l’approbation est synchronisée avec Teams. (Eden peut également voir et approuver la demande dans Shifts). Alex est informé dans Teams que sa demande est approuvée et affiche son calendrier mis à jour.

Alex veut échanger un shift avec un collègue. Dans Shifts, Alex voit une liste de tous les shifts qui sont éligibles à un échange en fonction des règles d’entreprise dans Blue Yonder WFM. Alex choisit un shift actuellement affecté à Gena. Gena est averti dans Teams sur son appareil mobile et accepte la demande d’échange. Eden voit et approuve la demande dans Shifts, et l’approbation est synchronisée avec blue Yonder WFM. (Eden peut également voir et approuver la demande dans blue Yonder WFM). Alex et Gena sont avertis dans Teams et affichent leurs planifications mises à jour.

#### <a name="set-up-a-connection"></a>Configurer une connexion

L’intégration de Shifts à Blue Yonder WFM à l’aide du connecteur ne prend que quelques étapes. Vous pouvez utiliser l’Assistant Connecteur Shifts dans le Centre d'administration Microsoft 365 pour configurer rapidement une connexion. L’Assistant configure le connecteur en fonction des paramètres que vous choisissez et crée la connexion. Si vous préférez utiliser PowerShell, nous fournissons également des scripts PowerShell que vous pouvez utiliser pour vous connecter.

Pour obtenir des conseils pas à pas, consultez :

- [Utiliser l’Assistant Connecteur Shifts pour connecter Shifts à Blue Yonder Workforce Management](shifts-connector-wizard.md)
- [Utiliser PowerShell pour connecter Shifts à Blue Yonder Workforce Management](shifts-connector-blue-yonder-powershell-setup.md)

Une fois la connexion configurée, vous pouvez utiliser PowerShell pour mettre à jour et modifier les paramètres de connexion à tout moment, si nécessaire. En ce qui concerne le connecteur lui-même, vous n’avez pas besoin de vous soucier des mises à niveau ou de la maintenance. On s’en occupe.

### <a name="reflexis-shifts-connector-for-microsoft-teams"></a>Connecteur Reflexis Shifts pour Microsoft Teams

Le connecteur Reflexis Shifts pour Microsoft Teams est hébergé et géré par Zebra. Avec ce connecteur, vous pouvez intégrer Shifts au système WFM Reflexis pour gérer vos planifications et les tenir à jour.

Les travailleurs de première ligne ont accès à leur horaire dans Shifts in Teams, et leurs demandes sont synchronisées entre Shifts et Reflexis Workforce Scheduler (RWS). L’état des demandes et des décalages créés dans RWS est synchronisé avec Shifts dans Teams.

:::image type="content" source="../../media/shifts-connector-reflexis.png" alt-text="Capture d’écran montrant la liste des décalages sur un appareil mobile et une planification dans Reflexis." lightbox="../../media/shifts-connector-reflexis.png":::

Les responsables de première ligne peuvent :

- Publiez des décalages et des planifications dans Reflexis et affichez-les dans Shifts.
- Modifiez les décalages dans reflexis et shifts.
- Créez, gérez et attribuez des décalages ouverts dans Reflexis et Shifts.
- Affichez et approuvez les demandes de planification des travailleurs dans Reflexis et Shifts.

Les travailleurs de première ligne peuvent :

- Consultez les horaires et les horaires de leur équipe et de leur équipe dans Shifts.
- Demandez un congé, ouvrez des équipes, échangez et proposez des changements dans Shifts.

Pour en savoir plus, accédez à https://connect.zebra.com/microsoft-connectors.

## <a name="open-source-shifts-connectors"></a>Connecteurs Shifts open source

Les connecteurs Shifts open source sont des intégrations basées sur la communauté [basées sur shifts Graph API](/graph/api/resources/shift). Les connecteurs open source suivants sont disponibles :

- Kronos-to-Teams WFC local
- Connecteur JDA-to-Teams Shifts (pour Blue Yonder version 2017 à 2020.2)

Chaque connecteur est fourni avec des instructions de déploiement et de configuration détaillées. Ils incluent des scripts de déploiement Azure Resource Manager (ARM) qui vous permettent d’héberger tous les services nécessaires dans Microsoft Azure. Le code source et les scripts de déploiement sont disponibles en téléchargement dans un [dépôt GitHub](https://github.com/OfficeDev/Microsoft-Teams-Shifts-WFM-Connectors). Vous pouvez effectuer un déploiement tel quels ou personnaliser ou étendre pour répondre à vos besoins.

Pour plus d’informations, consultez les [connecteurs Shifts prêts pour la production](/microsoftteams/platform/samples/shifts-wfm-connectors).

## <a name="related-articles"></a>Articles connexes

- [Gérer l’application Shifts](manage-the-shifts-app-for-your-organization-in-teams.md)
