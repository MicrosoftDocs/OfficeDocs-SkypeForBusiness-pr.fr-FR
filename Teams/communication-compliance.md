---
title: Conformité de la communication pour Microsoft teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anwara
description: En savoir plus sur la conformité des communications, qui fait partie de la solution de risque Insider de Microsoft Teams (incluse dans la fonctionnalité de conformité des communications M365).
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bf97f4adc33b0855e986cf2baed54f69de91f4f0
ms.sourcegitcommit: c8b5d4dd70d183f7ca480fb735a19290a3457b30
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/08/2020
ms.locfileid: "45077692"
---
# <a name="communication-compliance-for-microsoft-teams"></a>Conformité de la communication pour Microsoft teams

La conformité aux communications fait partie de la nouvelle solution de risque Insider dans Microsoft 365 qui permet de réduire les risques de communication en vous aidant à détecter, capturer et utiliser les actions de correction pour les messages inappropriés au sein de votre organisation. Il permet d’identifier le langage injurieux et le harcèlement dans les canaux d’équipe ou 1:1 et les discussions de groupe. Vous pouvez également définir des stratégies pour voir si des informations sensibles sont partagées dans le cadre de canaux d’équipe ou de la 1:1 et des discussions de groupe. Pour plus d’informations sur les différents types de stratégies et la façon de procéder à la configuration, reportez-vous à l' [article M365](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance).

## <a name="how-to-use-communication-compliance-in-teams"></a>Utilisation de la conformité de la communication dans teams

### <a name="identify-inappropriate-messages"></a>Identifier les messages indésirables

Si vous voulez identifier les messages envoyés dans Microsoft Teams (1:1, les conversations de groupe ou les conversations de canal), vous pouvez activer les stratégies pour détecter ce problème et le réviseur peut consulter les messages et prendre les mesures nécessaires comme envoyer du matériel de formation ou faire remonter aux autorités appropriées.

### <a name="identify-sensitive-or-regulatory-information"></a>Identifier les informations sensibles ou réglementaires

Si vous souhaitez analyser les messages envoyés dans Microsoft Teams (1:1, discussions de groupe ou conversations de canal) pour les informations sensibles ou les types de réglementation, vous pouvez choisir des stratégies qui prennent en charge les types de conformité ou sensibles prédéfinis.

> [!NOTE]
> Les canaux privés ne sont pas pris en charge par la conformité des communications.

### <a name="custom-policy"></a>Stratégie personnalisée

Utilisez ce modèle pour configurer des canaux de communication spécifiques, des conditions de détection individuelles et la quantité de contenu à surveiller et à réviser au sein de votre organisation.

### <a name="custom-trainable-classifier"></a>Classificateur pour le convoi personnalisé

Utilisez des classifieurs à la demande quand l’un des classifieurs prêts à l’emploi ne répond pas à vos besoins. Le classificateur Microsoft 365 est un outil qui vous permet d’apprendre à reconnaître divers types de contenu en leur fournissant des exemples. Formation le classificateur implique d’abord de lui donner des exemples qui sont sélectionnés par l’utilisateur et qui correspondent à la catégorie. Ensuite, après avoir traité ces exemples, vous testez les prédictions en lui donnant un mélange d’échantillons positifs et négatifs. Pour plus d’informations à ce sujet, reportez-vous à l' [article M365](https://docs.microsoft.com/microsoft-365/compliance/classifier-creating-a-trainable-classifier) pour plus d’informations sur cette rubrique.

> [!NOTE]
> La conformité des communications prend désormais en charge les déploiements hybrides Exchange.

Compliance Compliance prend en charge l’historique des conversations pour les messages correspondant aux stratégies. Cela fournit un contexte à l’examen de l’administrateur.

:::image type="content" source="media/communication-compliance-1.png" alt-text="Écran de conformité de la communication dans Microsoft Teams.":::

## <a name="where-communication-policies-can-be-applied-in-teams"></a>Où les stratégies de communication peuvent être appliquées dans teams

Les stratégies de conformité des communications peuvent être configurées pour les messages envoyés en équipe aux niveaux suivants :

- Niveau utilisateur : un administrateur peut configurer des stratégies à un niveau utilisateur individuel ou l’appliquer à tous les utilisateurs du client. Cela ne concerne que les messages envoyés par un utilisateur dans 1:1 ou les discussions de groupe.
- Niveau d’équipe : un administrateur peut également configurer des stratégies pour une équipe. Tous les messages envoyés dans ce canal par l’équipe (messages de canal privé ne sont pas pris en charge).
