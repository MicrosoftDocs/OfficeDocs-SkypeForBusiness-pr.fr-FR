---
title: Présentation de la gestion des salles de Microsoft teams
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
ms.date: 5/10/2018
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
ms.collection:
- M365-collaboration
description: Présentation de la gestion des salles de Microsoft Teams.
ms.openlocfilehash: cff0b300dc6cc9f3c15e21163554571d49e6540c
ms.sourcegitcommit: 70bf1669442bbb50cb293c86d6a0c80fb3b2b55a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2019
ms.locfileid: "38675812"
---
# <a name="management-overview"></a>Vue d’ensemble de la gestion

Il est essentiel de développer et d’exécuter les opérations de maintenance et d’exécution en continu pour vous assurer que vos systèmes de salle Microsoft teams sont disponibles pour vos utilisateurs et offrir ainsi une bonne utilisation de l’utilisateur. 

## <a name="monitoring"></a>Surveillance 

Le contrôle des systèmes de salle Microsoft teams comporte deux activités clés :

- Surveillance de périphériques, d’applications et de périphériques
- Surveillance de la qualité et de la fiabilité (bord)

### <a name="microsoft-teams-rooms-device-application-and-peripheral-device-monitoring"></a>Analyse du périphérique, de l’application et de l’appareil périphériques de Microsoft teams

Pour garantir que les utilisateurs peuvent utiliser les unités de salles de Microsoft Teams, les unités doivent être activées, connectées au réseau avec l’application Microsoft teams de Microsoft correctement configurée et être connectées aux périphériques de fonctionnement. 

Les informations relatives à l’état de l’application Microsoft teams salles et aux périphériques connectés sont écrites par l’application Microsoft teams dans le journal des événements Windows et expliquées dans les [entrées du journal](azure-monitor-manage.md#understand-the-log-entries). 

|**Paramètre**|**Permet**|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (DWORD) 1  <br/> |Permet au démarrage de Microsoft teams  <br/> |
|Gestion de l'\> alimentation-sur le ca, éteindre l’écran après 10 minutes  <br/> Gestion de l'\> alimentation-sur le secteur, jamais mettre le système en veille  <br/> |Activation de l’affichage et de la réactivation des salles de Microsoft teams  <br/> |
|net accounts /maxpwage:unlimited  <br/> Ou équivalent signifie la désactivation de l’expiration du mot de passe sur le compte local. Si vous n’effectuez pas cette opération, le compte Skype ne parviendra pas à se connecter en signalant l’expiration d’un mot de passe. Note que ceci aura un impact sur tous les comptes locaux sur l’ordinateur, et par conséquent, cet échec entraînera aussi l’éventuelle expiration du compte administratif.  <br/> |Active le compte Skype avec lequel toujours se connecter  <br/> |

Pour transférer des fichiers à l’aide de stratégies de groupe, voir [configurer un élément de fichier](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx).
  
## <a name="remote-management-using-powershell"></a>Gestion distante à l’aide de PowerShell
<a name="RemotePS"> </a>

Nous vous recommandons d’utiliser Microsoft Operations Manager suite pour surveiller vos systèmes de salle Microsoft Teams. Pour obtenir des instructions sur la configuration de la surveillance et l’alerte de base, voir [déployer la gestion des salles de Microsoft teams avec Azure Monitor](azure-monitor-deploy.md). 

Grâce à ces instructions, vous pouvez créer un tableau de bord simple à utiliser pour identifier les problèmes liés à l’utilisation de vos unités de salle Microsoft teams au sein de votre déploiement. 

|    |     |
|-----------|------------|
|![](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Vérifiez que vous utilisez la suite de gestion des opérations pour surveiller votre déploiement de Microsoft Teams.</li><li>Déterminez la liste de distribution cible à utiliser pour les alertes par e-mail.</li></ul>|
|![](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Définissez votre approche de qualité et de surveillance de la fiabilité.</li></ul>|

## <a name="quality-and-reliability-monitoring-cqd"></a>Surveillance de la qualité et de la fiabilité (bord)

Nous vous conseillons d’implémenter les procédures de vérification de la qualité opérationnelle et de la fiabilité dans le cadre de votre déploiement pour contrôler la tendance des appels et de la qualité des réunions et de la fiabilité, en identifiant les zones de préoccupation et en vous efforçant de résoudre le problème. 

Lorsque vous chargez vos informations de bâtiment dans bord, vous pouvez examiner les tendances en matière de qualité d’appel et de fiabilité d’un niveau par niveau, ce qui permet de comparer facilement les bâtiments et de focaliser votre attention sur des problèmes spécifiques.

Nous vous recommandons de revoir et de suivre le Guide de la [qualité de l’utilisation](https://aka.ms/qerguide) pour identifier les tendances en matière de qualité et de fiabilité, et créer un plan d’action pour les résoudre. 

## <a name="updating-the-microsoft-teams-rooms-os-and-microsoft-teams-rooms-application"></a>Mise à jour du système d’exploitation Microsoft teams et de l’application Microsoft teams

Nous vous recommandons de mettre à jour l’application système d’exploitation de Microsoft teams et de Microsoft teams pour bénéficier des mises à jour et des améliorations du produit. Pour obtenir une aide détaillée, voir [gérer les salles de Microsoft teams](room-systems-v2-operations.md#software-updates). 

## <a name="windows-updates"></a>Mises à jour Windows

Microsoft teams Room s’exécute sur Windows 10 entreprise IoT ou Windows 10 entreprise (VL) et reçoit les mêmes mises à jour Windows et les mêmes versions de système d’exploitation que le bureau standard. Pour plus d’informations, voir [gérer les mises à jour Windows](updates.md) .


## <a name="troubleshooting"></a>Résolution des problèmes

Nous vous recommandons de configurer l’alerte de la suite de gestion des opérations comme décrit dans la section ci-dessus pour que votre équipe et votre support technique soient avertis de tout problème de Microsoft Teams. Les options qui s’offrent à vous pour la gestion à distance PowerShell sont décrites dans [gestion à distance à l’aide de PowerShell](room-systems-v2-operations.md#remote-management-using-powershell). Dans le cas où un périphérique est déconnecté, vous devrez peut-être vous reposer sur des « mains actives » locales ou sur la prise en charge de l’examen et de la reconnexion des appareils. 

Pour plus d’informations sur la résolution des problèmes et le mode administrateur, voir [gérer les salles de Microsoft teams](room-systems-v2-operations.md#admin-mode-and-device-management). 


## <a name="see-also"></a>Voir aussi

[Aide Microsoft Teams Rooms](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Plan pour les salles de Microsoft teams](skype-room-systems-v2-0.md)

[Déploiement de salles de Microsoft teams](room-systems-v2.md)

[Configurer une console de salle Microsoft teams](console.md)

[Gérer les paramètres de la console salles de Microsoft teams à distance à l’aide d’un fichier de configuration XML](xml-config-file.md)
