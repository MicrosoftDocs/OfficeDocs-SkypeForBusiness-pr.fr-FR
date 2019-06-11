---
title: 'Lync Server 2013: afficher les mises à jour logicielles pour les appareils de votre organisation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View software updates for devices in your organization
ms:assetid: d2cca12b-ed43-4e1f-90ab-d14bca8b482c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182592(v=OCS.15)
ms:contentKeyID: 48185418
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06700e198dcd1923e875401b4539a0af84417c44
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846289"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-software-updates-for-devices-in-lync-server-2013"></a>Afficher les mises à jour logicielles des appareils dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-11-01_

Avec Lync Server 2013, vous utilisez le service Web de mise à jour des périphériques pour afficher et gérer les mises à jour logicielles des appareils de votre organisation. Ces mises à jour sont disponibles dans des fichiers. cab (CAB) sur le site Web du [http://go.microsoft.com/fwlink/p/?linkId=204091](http://go.microsoft.com/fwlink/p/?linkid=204091)support Microsoft à l’adresse. Après avoir téléchargé le fichier. cab, exécutez l’applet de passe **Import-CSDeviceUpdate** pour importer les règles de mise à jour de l’appareil à partir du fichier. cab. Pour plus d’informations sur l’applet de connexion **Import-CSDeviceUpdate** , voir [Import-CSDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) dans la documentation Lync Server Management Shell.

<div>


> [!TIP]  
> Avant de déployer une nouvelle mise à jour de votre organisation, vérifiez qu’elle fonctionne correctement sur un appareil de test.



</div>

<div>

## <a name="to-view-software-updates-for-uc-devices"></a>Pour afficher les mises à jour logicielles des appareils UC

1.  À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Sur le site Web du support [http://go.microsoft.com/fwlink/p/?linkId=204091](http://go.microsoft.com/fwlink/p/?linkid=204091)Microsoft à, téléchargez le fichier. cab dans un emplacement sur un ordinateur Lync Server 2013 (par exemple,\\C: mises\\à jour UCUpdates. cab).

3.  Importez les règles de mise à jour\\de l’appareil\\à partir du fichier C: updates UCUpdates. cab en exécutant une des applets de commande suivantes:
    
      - Si le fichier. cab se trouve sur le même ordinateur que celui exécutant le service à mettre à jour (service: Redmond-WebSvc-2), exécutez l’applet de commande suivante:
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-2 -FileName C:\Updates\UCUpdates.cab
    
      - Si le fichier. cab se trouve sur un ordinateur autre que celui exécutant le service à mettre à jour (service: Redmond-WebSvc-3), exécutez l’applet de commande suivante:
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-3 -ByteInput C:\Updates\UCUpdates.cab

4.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

5.  Dans la barre de navigation gauche, cliquez sur **clients**, puis cliquez sur **mise à jour**de l’appareil.

6.  Dans la page **mise à jour** de l’appareil, cliquez sur une mise à jour dans la liste, puis effectuez l’une des opérations suivantes:
    
      - **Annuler une mise à jour en attente.** Pour empêcher le déploiement de la mise à jour sélectionnée sur les appareils de votre organisation, cliquez sur le menu **action** , puis cliquez sur **annuler les mises à jour en attente**.
    
      - **Approuver une mise à jour.** Pour autoriser le déploiement de la mise à jour sélectionnée sur les appareils de votre organisation, cliquez sur le menu **action** , puis cliquez sur **approuver**.
    
      - **Restaurer une mise à jour.** Pour autoriser la mise à jour des mises à jour précédemment approuvées sur les appareils de votre organisation, cliquez sur le menu **action** , puis cliquez sur **restaurer**.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Gestion des appareils, des téléphones et des applications client dans Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

