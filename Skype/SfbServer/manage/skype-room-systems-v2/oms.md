---
title: Gestion des appareils Skype Room Systems v2 avec OMS
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 5/19/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f8109905-3279-475f-a64b-31d37af48bfe
description: 'Cet article traite de la procédure de gestion intégrée et de bout en bout des appareils Skype Room Systems v2 avec Microsoft Operations Management Suite. '
ms.openlocfilehash: 7c36203dd6f6a90ccdab801bc66ff31c4319a6e1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="manage-skype-room-systems-v2-devices-with-oms"></a>Gestion des appareils Skype Room Systems v2 avec OMS
 
Cet article traite de la procédure de gestion intégrée et de bout en bout des appareils Skype Room Systems v2 avec Microsoft Operations Management Suite.  
  
Vous pouvez configurer Microsoft Operations Management Suite (OMS) pour fournir de télémétrie de base qui vous aideront à gérer Skype (voir le [Plan Skype salle v2 SMS avec OMS](../../plan-your-deployment/clients-and-devices/oms-management.md) et [déployer Skype salle v2 SMS avec OMS des équipements de salle de réunion ](../../deploy/deploy-clients/with-oms.md)pour plus de détails). Une fois que votre solution de gestion acquiert sa maturité, vous pouvez acheter des capacités de données et de gestion supplémentaires pour créer des vues plus précises des performances des appareils.
  
## <a name="understand-the-log-entries"></a>Comprendre les entrées de journal
<a name="Telemetry"> </a>

Les descriptions d';événements suivantes sont insérées dans le champ de description des journaux des événements toutes les cinq minutes, alors que l';application SRS enregistre les informations correspondantes dans le journaux des événements Windows. L’agent de l’OMS transmet ces rapports au OMS, qui les traite dans le tableau de bord que vous avez créé [déployer Skype salle de gestion](../../deploy/deploy-clients/with-oms.md)de systèmes v2 avec OMS. Le tableau de bord vous permet de consulter les entrées de journal individuelles afin de déterminer les mesures à prendre, le cas échéant. 
  
Les ID d'événement 2000 et 3000 indiquent que l'appareil concerné fonctionne correctement. Les ID d'événement 2001 et 3001 indiquent qu'un problème a été détecté. L'ID d'événement 4000 peut nécessiter une action s'il apparaît plus fréquemment que prévu, par rapport à la ligne de base que vous avez définie ou aux autres appareils déployés dans votre organisation.
  
Comprendre ces descriptions d'événements vous permet d'être rapidement informé(e) des problèmes et de disposer d'un point de départ pour le dépannage.
  
|**L’ID d’événement <br/> niveau**|**Comportement de l’événement**|**Description de l’événement**|
|:-----|:-----|:-----|
|2000  <br/> Information  <br/> | Il s'agit d'un événement de pulsation sain. Toutes les 5 minutes, SRS v2 vérifie qu’il est connecté à Skype pour les entreprises et a du réseau et connectivité de Microsoft Exchange. Si les 3´facteurs sont vrais, l'application écrit l'ID d'événement 2000 dans le journal des événements toutes les 5 minutes jusqu'à ce que l'appareil soit hors ligne ou que l'une ou plusieurs des conditions ne soient plus remplies. <br/> |  {"Description" :"Heartbeat is healthy.", "ResourceState":"Healthy", "OperationName":"Heartbeat", "OperationResult":"Pass","OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias@contoso.com","DisplayName":"Display name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"IP v6 address"} <br/> Dans cet exemple, toutes les conditions de pulsation ont été remplies et l'appareil SRS v2 a été marqué comme étant sain. S'il y avait eu des erreurs, l'application aurait enregistré à la place l'ID d'événement 2001.  <br/> |
|2001  <br/> Erreur  <br/> |Il s'agit d'un événement d'erreur d'application. Toutes les 5 minutes, SRS v2 vérifie s'il est connecté à Skype Entreprise avec un réseau et une connectivité d'Exchange. Si un ou plusieurs de facteurs sont faux, l'application écrit l'ID d'événement 2001 dans le journal des événements toutes les 5 minutes jusqu'à ce que l'appareil soit hors ligne et que toutes les conditions puissent être à nouveau remplies.  <br/> |  {"Description" :"Network status : Healthy. Exchange status : Connected. **Signin status: Unhealthy.** ","ResourceState":"Unhealthy","OperationName":"Heartbeat","OperationResult":"Fail","OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"","DisplayName":"Display Name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10","IPv6Address":"ip v6 address"}<br/> Dans cet exemple, SRSv2 a déterminé que la connexion réseau était saine et que l'application était connectée à Exchange, mais la partie en gras indique que l'application n'est pas connectée à Skype Entreprise. Il peut s'agir d'un problème de configuration au niveau de l'appareil ou de l'hôte.  <br/> L'état du réseau sera indiqué comme étant sain ou défectueux. Si l'état est Défectueux, il y a peut-être un problème de réseau ou l'appareil a peut-être été débranché (mais dans ce cas, il y a probablement également des erreurs au niveau d'Exchange et de Skype Entreprise).<br/> L’état d’Exchange s’affichera comme connecté ou d’une des valeurs suivantes : déconnecté, connexion, AutodiscoveryError (l’erreur la plus couramment rencontrée), GeneralError ou ServerVersionNotSupported. Si l’état est connexion, attendez que le message d’état suivant est envoyé, pour les autres erreurs de soumettre l’affaire à un administrateur de l’expérience dans la résolution des problèmes liés à Exchange.  <br/> L'état de la connexion indiqué (indiquant que l'application est connectée à Skype Entreprise) sera Sain ou Défectueux. Si l'état est Défectueux, envoyez un technicien pour examiner le problème de plus près.<br/> |
|3000  <br/> Information  <br/> |Cet événement vérifie qu’une vérification du matériel a été exécutée et jugée sains. Toutes vérifications v2 SRS 5 minutes configuré des composants matériels tels que de la face avant de l’affichage de la salle, microphone, haut-parleurs et caméra sont connectés et qu’il fonctionne. Si tous les composants sont sains, l'application écrit l'ID d'événement 3000 dans le journal des événements. Cet événement continue à être écrit toutes les 5 minutes, sauf si un problème avec un appareil connecté se produit.  <br/> |{"Description" :"HardwareCheckEngine is healthy.","ResourceState":"Healthy", "OperationName":"HardwareCheckEngine","OperationResult":"Pass","OS":"Windows 10","OSVersion":"10.0.14393.693","Alias":"alias@contoso.com","DisplayName":"Display Name","AppVersion":"1.0.38.0","IPv4Address":"10.10.10.10","IPv6Address":"ip v6 address"}  <br/> Dans cet exemple, tous les contrôles du matériel ont réussi. S'il y avait eu des erreurs, l'application aurait enregistré à la place l'ID d'événement 3001.  <br/> |
|3001  <br/> Événement d’erreur  <br/> |Il s'agit d'un événement d'erreur de matériel. L'application SRS dispose d'un processus qui contrôle la santé des composants matériels connectés (écran à l'avant de la salle, microphone, haut-parleur, caméra) toutes les 5 minutes. Si un ou plusieurs composants sont défectueux, l'application écrit l'ID d'événement 3001 dans le journal des événements. Cet événement continue à être écrit toutes les 5 minutes jusqu'à ce que le problème avec l'appareil soit résolu.  <br/> |{« Description » : » **statut avant affichage de salle : incorrecte.** Configured display count is 2. Real display count is 0. **Conference Microphone status : Unhealthy.** Conference Speaker status : Healthy. Default Speaker status : Healthy. Camera status : Healthy. ","ResourceState":"Unhealthy","OperationName":"HardwareCheckEngine","OperationResult":"Fail","OS":"Windows 10","OSVersion":"10.0.14393.1198","Alias":"alias@contoso.com","DisplayName":"Yosemite conference room","AppVersion":"2.0.58.0","IPv4Address":"10.10.10.10","IPv6Address":"IPv6Address","IPv4Address2":"10.10.10.10"} <br/>  Les périphériques matériels sont indiqués comme étant sains ou défectueux. <br/> Dans cet exemple, deux écrans à l'avant de la salle sont connectés et aucun des deux n'est disponible actuellement. L'état du microphone de conférence est Défectueux, ce qui pourrait avoir plusieurs causes possibles. Étant donné que la dernière ressource n'a pas réussi le contrôle, l'état de celle-ci est indiqué comme étant Défectueux. Envoyez un technicien pour examiner le problème de plus près.  <br/> |
|4000  <br/> Information  <br/> |Il s'agit d'un événement de redémarrage de l'application. À chaque redémarrage de l'application, elle enregistre cet événement dans le journal des événements Windows.  <br/> | {"Description" :"App restarts.","ResourceState":"Healthy","OperationName":"Restart","OperationResult":"Pass","OS":"Windows 10","OSVersion":"10.0.14393.693","Alias":"alias@domain.com","DisplayName":"Display Name","AppVersion":"1.0.38.0","IPv4Address":"10.10.10.10","IPv6Address":"ip v6 address"} <br/> L'application Skype Entreprise peut redémarrer pour différentes raisons. Comparez la fréquence de redémarrage des appareils dans le même immeuble et dans des immeubles différents, en gardant à l'esprit les problèmes connus comme les variations de puissance et les pannes d'alimentation, qui peuvent être des indices pour les problèmes d'infrastructure.  <br/> |
   
## <a name="see-also"></a>Voir aussi
<a name="Telemetry"> </a>

#### 

[Planification de la gestion de v2 Skype salle systèmes avec OMS](../../plan-your-deployment/clients-and-devices/oms-management.md)
  
[Déployer une gestion systèmes de salle Skype v2 avec OMS](../../deploy/deploy-clients/with-oms.md)

