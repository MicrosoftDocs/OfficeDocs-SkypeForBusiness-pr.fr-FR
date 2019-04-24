---
title: Vue d’ensemble de la gestion des salles d’équipes Microsoft
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
ms.collection: M365-voice
description: Vue d’ensemble de la gestion des salles d’équipes Microsoft.
ms.openlocfilehash: a06ffc6bb0aa69b493c95a516946c322034913f8
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32208245"
---
# <a name="management-overview"></a>Vue d’ensemble de la gestion 

Il est essentiel de développer et exécuter la maintenance régulière et opérations pour vous assurer que vos systèmes salles d’équipes Microsoft sont disponibles pour vos utilisateurs et fournir un utilisateur un expérience. 

## <a name="monitoring"></a>Surveillance 

Surveillance des systèmes de salles d’équipes Microsoft se compose de deux activités clés :

-  APPAREIL, application et surveillance du périphérique

-  Qualité et la fiabilité de la surveillance (CQD)

### <a name="microsoft-teams-rooms-device-application-and-peripheral-device-monitoring"></a>Dispositif de salles d’équipes Microsoft, application et surveillance du périphérique

Pour vous assurer que les utilisateurs sont en mesure d’utiliser les unités de salles d’équipes Microsoft, les unités doivent se trouver sur concernant au réseau avec l’application Microsoft équipes salles correctement configurée et être connectées à des périphériques fonctionne. 


Pour plus d’informations sur l’état de l’application Microsoft équipes salles et les périphériques connectés sont écrits par l’application Microsoft équipes salles dans le journal des événements Windows et expliquées dans [comprendre les entrées du journal](azure-monitor.md#understand-the-log-entries). 

|**Paramètre**|**Permet de**|
|:-----|:-----|
|HKLM\Software\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (dword) 1  <br/> |Permet de salles d’équipes Microsoft amorçage  <br/> |
|Gestion - de l’alimentation\> sur CA, désactiver écran au bout de 10 minutes  <br/> Gestion - de l’alimentation\> sur CA, placez jamais système en mode veille  <br/> |Permet de salles d’équipes Microsoft activer affiche attaché et réactiver automatiquement  <br/> |
|net accounts /maxpwage:unlimited  <br/> Ou équivalent signifie la désactivation de l’expiration du mot de passe sur le compte local. Si vous n’effectuez pas cette opération, le compte Skype ne parviendra pas à se connecter en signalant l’expiration d’un mot de passe. Note que ceci aura un impact sur tous les comptes locaux sur l’ordinateur, et par conséquent, cet échec entraînera aussi l’éventuelle expiration du compte administratif.  <br/> |Active le compte Skype avec lequel toujours se connecter  <br/> |
   
Transfert de fichiers à l’aide de stratégies de groupe est traitée dans [un élément de fichier de configuration](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx).
  
## <a name="remote-management-using-powershell"></a>Gestion distante à l’aide de PowerShell
<a name="RemotePS"> </a>

Nous recommandons d’utiliser Microsoft Operations Manager Suite à surveiller vos systèmes salles d’équipes Microsoft. Pour obtenir des instructions sur la configuration de surveillance et les alertes de base, voir [gestion de déployer Microsoft équipes salles avec Azure moniteur](../../deploy/deploy-clients/azure-monitor.md). 

À l’aide de ce guide, vous pouvez créer un tableau de bord simple à utiliser pour identifier des problèmes avec des unités de vos salles d’équipes Microsoft dans votre déploiement. 

|    |     |
|-----------|------------|
|![](../../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Vérifiez que vous allez utiliser la Suite de gestion des opérations de déploiement de Microsoft équipes salles.</li><li>Décider de la liste de distribution cible que vous allez utiliser pour les alertes par courrier électronique.</li></ul>|
|![](../../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Définir votre qualité et la fiabilité approche de surveillance.</li></ul>|

## <a name="quality-and-reliability-monitoring-cqd"></a>Qualité et la fiabilité de la surveillance (CQD)

Nous vous recommandons d’implémenter qualité opérationnelle en cours et la fiabilité de la surveillance des procédures dans le cadre de votre déploiement pour surveiller les tendances d’appel et de qualité de la réunion et de fiabilité, qui identifie les zones d’intérêt et utilisation d’une résolution. 

Lorsque vous téléchargez vos informations de construction dans CQD vous pouvez examiner les tendances qualité et la fiabilité d’appel sur un niveau par construction, ce qui facilite la comparaison de bâtiments et concentrer votre attention sur des problèmes spécifiques. Pour plus d’informations, téléchargez le [Moniteur-CQD pour Skype pour Business remise en ligne et le Guide des opérations](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=6_2_0_15). 

Nous vous recommandons de consulter et suivre le [Guide Quality of Experience passez en revue](https://aka.ms/qerguide) pour identifier les tendances de qualité et la fiabilité et créer un plan d’action pour les résoudre. 

## <a name="updating-the-microsoft-teams-rooms-os-and-microsoft-teams-rooms-application"></a>Mise à jour de l’application Microsoft équipes salles de système d’exploitation et de salles d’équipes Microsoft

Il est recommandé que vous mettez à jour l’application du système d’exploitation salles d’équipes Microsoft et les salles d’équipes Microsoft afin de bénéficier de mises à jour et améliorations. Pour obtenir des instructions détaillées, voir [Gérer les salles d’équipes Microsoft](room-systems-v2-operations.md#software-updates). 

## <a name="windows-updates"></a>Mises à jour Windows

Salles d’équipes Microsoft s’exécute sur Windows 10 entreprise IoT ou entreprise de 10 Windows (VL) et reçoit les même versions mises à jour Windows et du système d’exploitation de bureau standard. Pour plus d’informations, voir [Gérer les mises à jour de Windows](updates.md) .


## <a name="troubleshooting"></a>Résolution des problèmes

Nous vous recommandons de configurer Suite de gestion des opérations d’alerte comme décrit dans la section ci-dessus afin que votre équipe chargée des opérations et le support technique seront informés de tous les problèmes salles d’équipes Microsoft. Les options dont vous disposez pour la gestion à distance PowerShell sont décrits dans la [gestion à distance à l’aide de PowerShell](room-systems-v2-operations.md#remote-management-using-powershell). Dans le cas où un périphérique est déconnecté, vous devrez peut-être s’appuient sur locales mains « actives » ou la prise en charge de l’informatique d’analyser et reconnectez les périphériques. 

Pour plus d’informations sur le mode de résolution des problèmes et d’administration, voir [Gérer les salles d’équipes Microsoft](room-systems-v2-operations.md#admin-mode-and-device-management). 


## <a name="see-also"></a>Voir aussi

[Aide Microsoft Teams Rooms](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Planifier des équipes Microsoft salles](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)

[Déployer les équipes Microsoft salles](../../deploy/deploy-clients/room-systems-v2.md)

[Configurer une console Microsoft équipes salles](../../deploy/deploy-clients/console.md)

[Gérer les paramètres de console de salles d’équipes Microsoft à distance avec un fichier de configuration XML](xml-config-file.md)
