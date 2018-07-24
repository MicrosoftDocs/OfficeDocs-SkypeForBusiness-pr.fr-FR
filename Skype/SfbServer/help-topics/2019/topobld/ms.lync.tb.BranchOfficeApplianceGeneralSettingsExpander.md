---
title: Expanseur des paramètres généraux du Branch Office Appliance
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.BranchOfficeApplianceGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 86860416-7c9b-49af-b9d2-658c172852de
ROBOTS: NOINDEX, NOFOLLOW
description: 'Pour modifier les paramètres d’un serveur Survivable Branch Appliance existant ou d’un serveur Survivable Branch Server, vous permettent des sections suivantes :'
ms.openlocfilehash: 2a0d0c7ec22baa781f1931f4be7ecfc67d6aa6be
ms.sourcegitcommit: 1f7299f535ec6b34f92301b4abc14d8922492eeb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21058866"
---
# <a name="branch-office-appliance-general-settings-expander"></a>Expanseur des paramètres généraux du Branch Office Appliance
 
Pour modifier les paramètres d’un serveur Survivable Branch Appliance existant ou d’un serveur Survivable Branch Server, vous permettent des sections suivantes :
  
- Paramètres généraux
    
- Paramètres de résilience
    
- Paramètres du serveur de médiation
    

Pour un serveur Survivable Branch Appliance ou serveur Survivable Branch Server, vous permettent des éléments suivants :
  
### <a name="general-settings"></a>Paramètres généraux

Le nom de domaine complet (FQDN) du serveur Survivable Branch Appliance ou serveur Survivable Branch Server. Modifiez le nom de domaine complet du serveur pour changer la valeur. Vous devez disposer d’un enregistrement d’hôte DNS (A) correspondant à la nouvelle valeur.
  
Vous pouvez sélectionner **Utiliser toutes les adresses IP configurées** ou **Limiter l’utilisation des services aux adresses IP sélectionnées**. Si vous sélectionnez **Limiter le service aux adresses IP définies**, vous définissez l’adresse IP principale utilisée par le serveur pour toutes les communications, à l’exception de la passerelle du réseau téléphonique commuté (RTC). Vous devez définir une adresse IP distincte pour l’utilisation du réseau téléphonique commuté.
  
Dans **Associations**, vous pouvez modifier ou spécifier les paramètres suivants :
  
- Associer un serveur d’archivage vous permet de sélectionner pour associer un serveur d’archivage avec le Survivable Branch Appliance ou serveur Survivable Branch Server. Vous pouvez sélectionner à partir d’un serveur d’archivage déjà définies en sélectionnant le serveur dans la liste déroulante ou cliquez sur **Nouveau** pour spécifier un nouveau serveur d’archivage.
    
    > [!IMPORTANT]
    > Avant de publier la nouvelle topologie que vous venez de définir, le serveur que vous spécifiez doit exister et être joint au domaine. 
  
- Associez le serveur de surveillance vous permet de sélectionner pour associer un serveur de surveillance avec le Survivable Branch Appliance ou serveur Survivable Branch Server. Vous pouvez sélectionner à partir d’un serveur de surveillance déjà définies en sélectionnant le serveur dans la liste déroulante ou cliquez sur **Nouveau** pour spécifier un nouveau serveur de surveillance.
    
- Associez Edge permet de pool, vous pouvez choisir d’associer un serveur Edge ou un pool au serveur Survivable Branch Appliance ou Survivable Branch Server. Vous pouvez sélectionner le serveur dans la liste déroulante à partir d’un serveur Edge ou d’un pool de serveurs Edge déjà défini ou cliquer sur **Nouveau** pour spécifier un nouveau serveur Edge ou un nouveau pool de serveurs Edge.
    
### <a name="resiliency"></a>Résilience

La résilience permet une très grande disponibilité du pool de serveurs d’inscriptions. Lorsqu’un serveur d’inscriptions de secours est configuré, il permet de prendre le relais d’un serveur d’inscriptions en cas d’échec du serveur d’inscriptions principal, ce qui permet aux utilisateurs de se connecter et de communiquer. Certains utilisateurs peuvent disposer de fonctionnalités réduites en fonction des systèmes qui ont échoué sur le serveur principal.
  
Dans la liste déroulante, sélectionnez le pool frontal Enterprise Edition ou Standard Edition serveur frontal qui agiront en tant que la sauvegarde du serveur d’inscriptions pour le Survivable Branch Appliance ou serveur Survivable Branch Server. Vous pouvez également sélectionner pour activer le basculement et secours sur les intervalles de temps. Permet d’activer les paramètres de temps de basculement et de secours (spécifiées en secondes) pour la détection automatique d’un serveur d’inscriptions ayant échoué et un délai de secours pour permettre le calcul automatique principal sauvegarder et peut prendre en charge le processus de serveur d’inscriptions.
  
> [!IMPORTANT]
> Lorsque vous définissez l’intervalle entre deux détections d’échec et de secours, veillez à ne pas entrer un intervalle qui entraînera le basculement et le secours si le serveur d’inscriptions ne répond pas pendant un court instant. Le serveur d’inscriptions peut cesser de répondre pendant de brefs instants en fonction du chargement du pool ou des serveurs. Les valeurs par défaut pour un serveur Survivable Branch Appliance ou un serveur Survivable Branch Server dans un site vers un pool ou serveur Standard Edition serveur frontal est 120 secondes pour le basculement et 240 secondes de secours. 
  
### <a name="mediation-server"></a>Serveur de médiation

Dans **Serveur de médiation**, vous pouvez spécifier les éléments suivants :
  
**Serveur de médiation colocalisé activé** la case à cocher n’est pas disponible sur un serveur Survivable Branch Appliance ou un serveur Survivable Branch Server car le serveur de médiation est colocalisé.
  
Vous définissez le port d’écoute sur les serveurs du pool pour le protocole TLS (Transport Layer Security). Par défaut, il s’agit du port 5067. Si vous sélectionnez **Activer le port TCP**, vous devez définir un protocole TCP pour le serveur de médiation colocalisé. Il s’agit d’un paramètre facultatif, et vous devez consulter la configuration requise de votre passerelle ou de votre réseau public commuté pour déterminer si vous en avez besoin. Par défaut, le port TCP est le port 5068.
  
Vous définissez les passerelles PSTN associées avec le serveur de médiation colocalisé. Si vous avez déjà défini des passerelles, ils seront disponibles à associer au serveur de médiation. Si vous n’avez pas défini de passerelle, mais que vous pouvez les définir, vous pouvez sélectionner **Nouveau**. Vous pouvez également supprimer les passerelles qui sont déjà configurées pour le serveur de médiation. Sélectionnez la passerelle, puis cliquez sur **Supprimer**.
  
Si vous disposez de plusieurs passerelles associé à un serveur de médiation, la première passerelle associée sera la passerelle par défaut. Si vous devez choisir une autre passerelle comme passerelle par défaut, sélectionnez la passerelle à utiliser par défaut, puis cliquez sur **Utiliser par défaut**.
  

Pour plus d’informations sur la définition et la configuration des paramètres pour le Survivable Branch Appliance ou serveur Survivable Branch Server, voir [Branch-Site Resiliency Solutions](http://technet.microsoft.com/library/1700f99b-709c-4e47-88eb-c0a5490e26e2.aspx).
  

