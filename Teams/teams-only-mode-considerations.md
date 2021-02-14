---
title: Considérations relatives au mode Teams uniquement
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 01/09/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: landerl
description: Les administrateurs peuvent en savoir plus sur la préparation d’une mise à niveau vers le mode Microsoft Teams uniquement dans le Centre d’administration Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- ms.teamsadmincenter.orgwidesettings.teamsupgrade.upgradetoteams
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 86c27d8619a436c6a77ab435cfcb2cc4133befe0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802374"
---
# <a name="teams-only-mode-considerations"></a>Considérations relatives au mode Teams uniquement

Si vous êtes un administrateur de votre organisation Microsoft 365 ou Office 365, vous verrez désormais l’option de mettre à niveau vers le mode Teams uniquement dans le Centre d’administration Microsoft Teams. Cette fonctionnalité vous permet de mettre à niveau des utilisateurs individuels ou l’ensemble du client.  

La mise à niveau vers le mode Teams uniquement offre aux utilisateurs tous les avantages de Microsoft Teams, le hub pour le travail d’équipe dans Microsoft 365 ou Office 365, via une expérience client unique. En outre, les utilisateurs en mode Teams uniquement reçoivent tous les appels et conversations dans Teams, que l’expéditeur utilise Skype Entreprise ou Teams, et bénéficient de la prise en charge d’interop et de fédération.

Bien que des milliers de clients ont réussi la mise à niveau vers Microsoft Teams, certains éléments peuvent influencer la chronologie de mise à niveau et l’expérience utilisateur de votre organisation en cours de route. En particulier, le fait d’avoir la possibilité de mettre à niveau ne signifie pas nécessairement que votre organisation est prête pour ce changement. Pour bénéficier de la meilleure expérience utilisateur, vérifiez que Teams répond à vos besoins en matière de collaboration et de communication, assurez-vous que votre réseau est prêt à prendre en charge Teams et implémentez votre plan de préparation des utilisateurs avant de les mettre à niveau vers Teams. 

> [!IMPORTANT]
> Si vous débutez votre planification de la mise à niveau, n’oubliez pas de consulter notre guide de mise à niveau [de Microsoft Teams.](upgrade-start-here.md) 

**Considérations en coexistence**: Les organisations qui utilisent déjà Skype Entreprise Online et/ou Skype Entreprise Server peuvent présenter Teams à leur environnement à un rythme qui répond à leurs besoins. Les organisations peuvent déployer Teams de façon incrémentielle auprès d’un ensemble d’utilisateurs souhaité, et les utilisateurs qui utilisent Teams peuvent communiquer avec les utilisateurs qui utilisent Skype Entreprise et inversement. Pour gérer cette expérience, les administrateurs utilisent les modes de coexistence qui définissent l’expérience client des utilisateurs finaux, le comportement de routage des conversations et appels entrants, ainsi que le fait que de nouvelles réunions soient programmées dans Teams ou Skype Entreprise. Les utilisateurs peuvent se fédérer avec des utilisateurs d’autres organisations si l’utilisateur est mis à niveau vers **Teams uniquement**; Toutefois, la meilleure expérience est fournie lorsque les deux utilisateurs utilisent Teams. Les utilisateurs qui ont été mis à niveau vers Teams uniquement peuvent toujours participer à des réunions Skype Entreprise. 

> [!IMPORTANT]
> Pour plus d’informations sur la coexistence, reportez-vous à Comprendre la coexistence et l’interopérabilité avec Microsoft Teams et [Skype Entreprise.](teams-and-skypeforbusiness-coexistence-and-interoperability.md) Pour plus d’informations sur Teams et Skype (grand public), consultez [Teams et l’interopérabilité de Skype.](teams-skype-interop.md)

**Considérations à l’échelle du** client : Nous travaillons à l’activation de Teams dans les environnements suivants ; toutefois, pour le moment, les administrateurs ne doivent pas mettre à niveau les utilisateurs de leur organisation si leur client Skype Entreprise est hébergé dans l’un des environnements suivants :

 - Office 365 géré par 21Vianet
 - Office 365 Germany
 - Le client Skype Entreprise est hébergé en Corée du **Sud** et l’organisation exige que les données Teams soient stockées en Corée du Sud. Actuellement, les organisations qui disposent de données Skype Entreprise stockées en Corée du Sud et qui font la mise à niveau vers Teams ont leurs données Teams stockées dans la région du centre de données Asie, et non dans la région du centre de données en Corée du Sud.

**Considérations spécifiques** à l’utilisateur : Certains scénarios d’utilisateurs évoluent toujours et les administrateurs peuvent décider de différer temporairement la mise à niveau de certains utilisateurs lors de la mise à niveau d’autres utilisateurs dans l’organisation. En particulier, nous travaillons toujours sur la recherche de scénarios pour les utilisateurs dont l’appareil principal est VDI. Pour les annonces, veuillez surveiller le site de feuille de route [Microsoft 365.](https://www.microsoft.com/microsoft-365/roadmap)

> [!NOTE]
> Avant de passer en mode Teams uniquement, vous devez remplacer ou mettre à jour les appareils qui ne supportent pas Teams. 

> [!IMPORTANT]
> **N’oubliez** pas que le déplacement vers Teams est bien plus qu’une migration technique. Une mise à niveau réussie évalue la préparation technique et la préparation des utilisateurs finux. Pour plus d’informations [](upgrade-framework.md) sur la planification de l’implémentation de votre mise à niveau vers Teams, voir nos conseils de mise à niveau de Skype Entreprise vers Teams.  
