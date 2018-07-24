---
title: Présentation de la gestion de systèmes de salle Skype v2
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
description: Vue d’ensemble de la gestion de systèmes de salle Skype v2.
ms.openlocfilehash: 81ad0e43f68127e3a178434ebdd8ac8a43c94adc
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21014902"
---
# <a name="management-overview"></a>Vue d’ensemble de la gestion 

Il est essentiel de développer et exécuter la maintenance régulière et opérations pour vous assurer que votre v2 Skype salle systèmes sont disponibles pour vos utilisateurs et fournir un utilisateur un expérience. 

## <a name="monitoring"></a>Surveillance 

Surveillance v2 Skype salle systèmes se compose de deux activités clés :

-  APPAREIL, application et surveillance du périphérique

-  Qualité et la fiabilité de la surveillance (CQD)

### <a name="skype-room-systems-v2-device-application-and-peripheral-device-monitoring"></a>Systèmes de salle Skype v2 DISPOSITIF, application et surveillance du périphérique

Pour vous assurer que les utilisateurs sont en mesure d’utiliser les unités de v2 Skype salle systèmes, les unités doivent se trouver sur concernant au réseau avec l’application v2 de systèmes de salle Skype correctement configurée et être connectées à des périphériques fonctionne. 


Plus d’informations sur l’état de l’application v2 de Skype salle systèmes et périphériques connectés est écrit par l’application v2 de systèmes de salle Skype pour le journal des événements Windows et expliquée [dans cet article](oms.md#understand-the-log-entries). 

|**Paramètre**|**Permet de**|
|:-----|:-----|
|HKLM\Software\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (dword) 1  <br/> |V2 de systèmes de salle Skype permet de démarrer  <br/> |
|Gestion - de l’alimentation\> sur CA, désactiver écran au bout de 10 minutes  <br/> Gestion - de l’alimentation\> sur CA, placez jamais système en mode veille  <br/> |Permet de systèmes de salle Skype v2 activer affiche attaché et réactiver automatiquement  <br/> |
|net accounts /maxpwage:unlimited  <br/> Ou équivalent signifie la désactivation de l’expiration du mot de passe sur le compte local. Si vous n’effectuez pas cette opération, le compte Skype ne parviendra pas à se connecter en signalant l’expiration d’un mot de passe. Note que ceci aura un impact sur tous les comptes locaux sur l’ordinateur, et par conséquent, cet échec entraînera aussi l’éventuelle expiration du compte administratif.   <br/> |Active le compte Skype avec lequel toujours se connecter  <br/> |
   
Transfert de fichiers à l’aide de stratégies de groupe est traitée dans [un élément de fichier de configuration](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx).
  
## <a name="remote-management-using-powershell"></a>Gestion distante à l’aide de PowerShell
<a name="RemotePS"> </a>


Nous recommandons d’utiliser Microsoft Operations Manager Suite à surveiller vos systèmes de v2 Skype salle. Pour obtenir des instructions sur la configuration de surveillance et les alertes de base, voir [déployer Skype salle v2 SMS avec OMS](../../deploy/deploy-clients/with-oms.md). 

À l’aide de ce guide, vous pouvez créer un tableau de bord simple à utiliser pour identifier des problèmes avec des unités v2 de vos systèmes de salle Skype dans votre déploiement. 

|    |     |
|-----------|------------|
|![](../../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Vérifiez que vous allez utiliser la Suite de gestion des opérations de déploiement de v2 Skype salle systèmes.</li><li>Décider de la liste de distribution cible que vous allez utiliser pour les alertes par courrier électronique.</li></ul>|
|![](../../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Définir votre qualité et la fiabilité approche de surveillance.</li></ul>|

## <a name="quality-and-reliability-monitoring-cqd"></a>Qualité et la fiabilité de la surveillance (CQD)

Nous vous recommandons d’implémenter qualité opérationnelle en cours et la fiabilité de la surveillance des procédures dans le cadre de votre déploiement pour surveiller les tendances d’appel et de qualité de la réunion et de fiabilité, qui identifie les zones d’intérêt et utilisation d’une résolution. 

Lorsque vous téléchargez vos informations de construction dans CQD vous pouvez examiner les tendances qualité et la fiabilité d’appel sur un niveau par construction, ce qui facilite la comparaison de bâtiments et concentrer votre attention sur des problèmes spécifiques. Pour plus d’informations, téléchargez le [Moniteur-CQD pour Skype pour Business remise en ligne et le Guide des opérations](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=6_2_0_15). 

Nous vous recommandons de consulter et suivre le [Guide Quality of Experience passez en revue](https://aka.ms/qerguide) pour identifier les tendances de qualité et la fiabilité et créer un plan d’action pour les résoudre. 

## <a name="updating-the-skype-room-systems-v2-os-and-skype-room-systems-application"></a>Mise à jour de l’application du système d’exploitation et systèmes de salle Skype de v2 Skype salle systèmes 

Il est recommandé que vous mettez à jour Skype salle systèmes v2 OS Skype salle systèmes v2 à l’application et tirent parti des améliorations et des mises à jour de produit. Pour obtenir des instructions détaillées, voir [Gérer les systèmes de salle Skype v2](room-systems-v2-operations.md#software-updates). 

## <a name="troubleshooting"></a>Identification et résolution des problèmes

Nous vous recommandons de configurer Suite de gestion des opérations d’alerte comme décrit dans la section ci-dessus afin que votre équipe chargée des opérations et le support technique seront informés de tous les systèmes de salle Skype v2 problèmes. Les options dont vous disposez pour la gestion à distance PowerShell sont décrits dans la [gestion à distance à l’aide de PowerShell](room-systems-v2-operations.md#remote-management-using-powershell). Dans le cas où un périphérique est déconnecté, vous devrez peut-être s’appuient sur locales mains « actives » ou la prise en charge de l’informatique d’analyser et reconnectez les périphériques. 

Pour plus d’informations sur le mode de résolution des problèmes et d’administration, voir [Gérer les systèmes de salle Skype v2](room-systems-v2-operations.md#admin-mode-and-device-management). 

## <a name="see-also"></a>Voir aussi

[Systèmes de salle Skype version 2](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Planification de Skype Room Systems v2](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)

[Déploiement de Skype Room System v2](../../deploy/deploy-clients/room-systems-v2.md)

[Configuration d’une console Skype Room Systems v2](../../deploy/deploy-clients/console.md)

[Gestion à distance des paramètres d'une console Skype Room Systems v2 à l'aide d'un fichier de configuration XML](xml-config-file.md)
