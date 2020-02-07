---
title: Considérations relatives au mode Teams uniquement
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 01/09/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: dearbeen
description: Préparer la mise à niveau vers le mode Microsoft teams uniquement
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- ms.teamsadmincenter.orgwidesettings.teamsupgrade.upgradetoteams
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d9ad590f61b63aad1208fb2ad04f4aa3b80a3ddb
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836974"
---
# <a name="teams-only-mode-considerations"></a>Considérations relatives au mode Teams uniquement

Si vous êtes un administrateur sur votre client 365 Office, vous verrez désormais l’option de mise à niveau vers le mode équipes uniquement dans le centre d’administration Microsoft Teams. Cette fonctionnalité vous permet de mettre à niveau des utilisateurs individuels ou tout le client.  

La mise à niveau vers le mode équipes uniquement offre aux utilisateurs les avantages complets de Microsoft Teams, le Hub pour le travail en équipe dans Office 365, par le biais d’une seule et même interface client. De plus, les utilisateurs en mode équipes uniquement recevront tous les appels et les discussions dans Teams, que l’expéditeur utilise ou non Skype entreprise ou équipes, et qu’il bénéficie d’une prise en charge de l’interopérabilité et de la Fédération.

Bien que des milliers de clients aient réussi la mise à niveau de Microsoft Teams, il existe des considérations qui peuvent influer sur la chronologie de la mise à niveau de votre organisation et son utilisation. Par exemple, si vous avez la possibilité de procéder à la mise à niveau, cela signifie que votre organisation est prête pour cette modification. Pour bénéficier de la meilleure expérience utilisateur, vérifiez que Teams répond à vos besoins en matière de collaboration et de communication, assurez-vous que votre réseau est prêt à prendre en charge Teams et implémentez votre plan de préparation des utilisateurs avant de les mettre à niveau vers Teams. 

> [!IMPORTANT]
> Si vous commencez à commencer votre planification de mise à niveau, veillez à passer en revue les ressources de mise à niveau et de planification complètes. [Commencez ici](upgrade-start-here.md). 

**Considérations de coexistence**: les organisations qui utilisent déjà Skype entreprise Online et/ou Skype entreprise Server peuvent proposer des équipes au rythme qui répondent à leurs besoins. Les organisations peuvent déployer de façon incrémentielle des équipes auprès d’un ensemble d’utilisateurs souhaité, et les utilisateurs qui utilisent teams peuvent communiquer avec des utilisateurs de Skype entreprise, et inversement. Pour gérer cette situation, les administrateurs utilisent les modes de coexistence, qui définissent l’utilisation du client de l’utilisateur final, le comportement de routage des conversations et des appels entrants, ainsi que la planification de nouvelles réunions dans teams ou Skype entreprise. Les utilisateurs peuvent se fédérer avec des utilisateurs d’autres organisations si l’utilisateur est mis à niveau vers **équipes uniquement**; Toutefois, la meilleure utilisation est fournie lorsque les deux utilisateurs utilisent Teams. Les utilisateurs qui sont mis à niveau vers les équipes peuvent toujours participer à des réunions Skype entreprise. 

> [!NOTE]
> Les utilisateurs qui sont mis à niveau vers Teams ne peuvent pas communiquer avec des utilisateurs de Skype pour particuliers.

> [!IMPORTANT]
> Pour plus d’informations sur la coexistence, reportez-vous à la rubrique comprendre le fonctionnement de [Microsoft Teams, de la coexistence et de l’interopérabilité de Skype entreprise](teams-and-skypeforbusiness-coexistence-and-interoperability.md). 

**Remarques relatives**à l’ensemble du client : nous travaillons à l’activation d’équipes dans les environnements suivants ; Toutefois, pour le moment, les administrateurs ne peuvent pas mettre à niveau les utilisateurs de leur organisation si leur client Skype entreprise est hébergé dans l’un des environnements suivants :

 - Communauté gouvernementale secteur public haut
 - Government Community Cloud DoD
 - Office 365 géré par 21Vianet
 - Office 365 Allemagne
 - Le client Skype entreprise est hébergé en Corée du Sud **et** l’organisation nécessite le stockage des données d’équipe en Corée du Sud. Pour l’instant, les organisations possédant des données Skype entreprise stockées en Corée du Sud qui effectuent une mise à niveau vers teams disposeront des données de leurs équipes dans la région du centre de données Asia, et non dans la région du centre de données de Corée du Sud

**Considérations spécifiques à l’utilisateur**: certains scénarios d’utilisation sont toujours évolutifs, et les administrateurs peuvent décider de différer temporairement la mise à niveau de certains utilisateurs lors de la mise à niveau d’autres utilisateurs au sein de l’organisation. En particulier, nous travaillons toujours sur des scénarios d’adressage pour les utilisateurs dont l’appareil principal est basé sur l’infrastructure VDI. Pour plus d’annonces, visitez le site de [plan d’évolution d’Office 365](https://www.microsoft.com/en-us/microsoft-365/roadmap) .

> [!NOTE]
> Avant de basculer vers le mode équipes uniquement, vous devez remplacer ou mettre à jour les appareils qui ne prennent pas en charge Teams. 

> [!IMPORTANT]
> **N’oubliez pas**que le déplacement vers teams n’est pas une migration technique. Une mise à niveau réussie évalue la compatibilité technique et celle de l’utilisateur final. Pour plus d’informations sur la planification d’une mise à niveau de Microsoft Teams, reportez-vous à la rubrique [recommandations de mise à niveau](upgrade-framework.md) de Skype entreprise vers équipes  
