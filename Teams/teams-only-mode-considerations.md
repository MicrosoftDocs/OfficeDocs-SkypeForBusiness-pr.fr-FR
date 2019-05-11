---
title: Considérations relatives au mode Teams uniquement
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 01/09/2019
ms.topic: conceptual
ms.service: msteams
ms.reviewer: dearbeen
description: Préparer votre mise à niveau vers le mode uniquement les équipes Microsoft
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
f1keywords: ms.teamsadmincenter.orgwidesettings.teamsupgrade.upgradetoteams
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c60c7436f406c5fe4084e00f26ad66ada12f181e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930333"
---
# <a name="teams-only-mode-considerations"></a>Considérations relatives au mode Teams uniquement

Si vous êtes un administrateur sur votre client Office 365, vous verrez maintenant l’option de mise à niveau vers le mode équipes uniquement dans le centre d’administration Microsoft Teams. Grâce à cette fonctionnalité vous pouvez mettre à niveau des utilisateurs individuels, soit également le client entière.  

Mise à niveau vers les équipes uniquement en mode offre aux utilisateurs le meilleur parti de Microsoft Teams, le concentrateur de travail d’équipe dans Office 365, via une expérience client unique. En outre, les utilisateurs en mode équipes uniquement recevra tous les appels et conversations dans les équipes, indépendamment de si l’expéditeur est à l’aide de Skype pour les équipes ou de l’entreprise et bénéficier de la prise en charge de l’interopérabilité et la fédération.

Alors que des milliers de clients ont été mis à niveau vers Microsoft Teams, il existe des considérations peuvent influer sur votre organisation mise à niveau chronologie et l’expérience utilisateur tout au long du processus. En particulier, la possibilité de mise à niveau ne signifie pas nécessairement que votre organisation est prête pour que cette modification. Pour bénéficier de la meilleure expérience utilisateur, vérifiez que Teams répond à vos besoins en matière de collaboration et de communication, assurez-vous que votre réseau est prêt à prendre en charge Teams et implémentez votre plan de préparation des utilisateurs avant de les mettre à niveau vers Teams. 

> [!IMPORTANT]
> Si vous débutez votre planification de la mise à niveau, veillez à consulter notre Guide de mise à niveau complète et la planification des ressources. [Commencez ici](upgrade-introduction.md). 

**Considérations relatives à la coexistence**: les organisations qui utilisent déjà Skype pour Business Online et/ou Skype pour Business Server peuvent introduire des équipes dans leur environnement à un rythme qui répond à leurs besoins. Les organisations peuvent incrémentielle déployer équipes à un ensemble d’utilisateurs souhaité selon vos besoins et utilisateurs qui utilisent les équipes peuvent communiquer avec les utilisateurs qui utilisent Skype pour les entreprises, et inversement. Pour gérer cette expérience, les modes de coexistence utiliser administrateurs, qui définissent l’expérience du client utilisateur final, le comportement de routage d’entrant conversations et les appels, ainsi que si les nouvelles réunions sont planifiées dans des équipes ou Skype pour les entreprises. Les utilisateurs peuvent se fédérer avec d’autres organisations si l’utilisateur est mis à niveau vers **Les équipes uniquement**; Toutefois, la meilleure expérience est fournie lorsque les deux utilisateurs utilisent des équipes. Les utilisateurs qui sont mis à niveau pour que les équipes peuvent tout de même rejoindre Skype pour les réunions d’entreprise. 

> [!NOTE]
> Les utilisateurs qui sont mis à niveau pour que les équipes ne peuvent pas communiquer avec des utilisateurs qui utilisent Skype pour consommateur.

> [!IMPORTANT]
> Pour plus d’informations sur la coexistence reportez-vous à [comprendre les équipes Microsoft et Skype pour l’interopérabilité et coexistence d’entreprise](teams-and-skypeforbusiness-coexistence-and-interoperability.md). 

**Considérations relatives au client à l’échelle**: nous effectuons travailler sur l’activation d’équipes dans les environnements suivants ; Toutefois, pour l’instant, les administrateurs ne doivent pas mettre à niveau tous les utilisateurs dans leur organisation si leur Skype pour client d’entreprise est hébergé dans un des environnements suivants :

 - Communauté gouvernement Cloud haute
 - Pour le gouvernement Communauté Cloud DoD
 - Office 365 exécuté par 21Vianet
 - Office 365 Allemagne
 - Skype pour client d’entreprise est hébergée dans Corée du Sud **et** que l’organisation nécessite des données équipes à stocker en Corée du Sud. Actuellement, les organisations avec Skype pour les données métiers stockées dans Corée du Sud aux équipes de mise à niveau aura leurs données équipes stockées dans la région Asie centre de données, pas dans la zone de centre de données Corée du Sud.

**Considérations spécifiques à l’utilisateur**: certains scénarios utilisateur évoluent, et les administrateurs peuvent choisir de temporairement différer la mise à niveau de certains utilisateurs lors de la mise à niveau d’autres utilisateurs dans l’organisation. Nous sommes en train d’adressage ces scénarios ; Contrôlez dans le site de la [Feuille de route Office 365](https://www.microsoft.com/en-us/microsoft-365/roadmap) pour les annonces.

| Scénario | Notes |
|----------|-------|
|Appareil de travail principal de l’utilisateur est un Mac et l’utilisateur doit voir disponibilité des collègues dans Outlook. | Présence Outlook dans les équipes n'est pas encore entièrement pris en charge pour les périphériques Mac. |
| Utilisateur est régulièrement organiser des réunions avec des clients ou partenaires externes dans différentes régions internationale. | Messagerie instantanée ne voyez pas les participants externes dont le client réside dans une autre géolocalisation conversation dans une réunion **fédérés** . Les participants peuvent tout de même rejoindre la réunion en tant qu’utilisateurs anonymes. |
| Utilisateur réalise Skype pour les réunions de diffusion d’entreprise. |  Alors que live équipes événements (diffusion Skype en remplaçant) est déjà dans la version d’évaluation, cet utilisateur devra peut-être restent sur Skype pour les entreprises jusqu'à la disponibilité générale d’événements en direct équipes.
| Périphérique principal de l’utilisateur est basée sur les VDI. | |
|||

> [!IMPORTANT]
> **N’oubliez pas**: le déplacement aux équipes est supérieure à une migration technique. Une mise à niveau réussie évalue la préparation technique et préparation de l’utilisateur final. Consultez notre Skype pour les entreprises à des équipes [des instructions de mise à niveau](upgrade-framework.md) pour plus d’informations sur la planification d’une implémentation de votre mise à niveau vers les équipes.  
