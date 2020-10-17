---
title: 'Lync Server 2013 : affichage des mises à jour logicielles pour les appareils de votre organisation'
description: 'Lync Server 2013 : affichage des mises à jour logicielles pour les périphériques de votre organisation.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View software updates for devices in your organization
ms:assetid: d2cca12b-ed43-4e1f-90ab-d14bca8b482c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182592(v=OCS.15)
ms:contentKeyID: 48185418
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 833ab25315847b760271c63bbfca3ba8357e41c1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558830"
---
# <a name="view-software-updates-for-devices-in-lync-server-2013"></a>Affichage des mises à jour logicielles pour les périphériques dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Avec Lync Server 2013, vous utilisez le service Web de mise à jour des périphériques pour afficher et gérer les mises à jour logicielles des appareils de votre organisation. Ces mises à jour sont disponibles dans les fichiers. cab (armoire) à partir du site Web du support technique de Microsoft à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=204091](https://go.microsoft.com/fwlink/p/?linkid=204091) . Après avoir téléchargé le fichier. cab, exécutez l’applet de commande **Import-CSDeviceUpdate** pour importer les règles de mise à jour des périphériques à partir du fichier. cab. Pour plus d’informations sur l’applet de commande **Import-CSDeviceUpdate** , voir [Import-CSDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) dans la documentation de Lync Server Management Shell.

<div>


> [!TIP]  
> Avant de déployer une nouvelle mise à jour dans votre entreprise, vérifiez qu’elle fonctionne correctement sur un périphérique de test.



</div>

<div>

## <a name="to-view-software-updates-for-uc-devices"></a>Pour afficher les mises à jour logicielles des périphériques de communications unifiées

1.  Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  À partir du site Web du support technique de Microsoft à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=204091](https://go.microsoft.com/fwlink/p/?linkid=204091) , téléchargez le fichier. cab vers un emplacement sur un ordinateur Lync Server 2013 (par exemple, C : \\ updates \\UCUpdates.cab).

3.  Importez les règles de mise à jour des périphériques à partir du fichier C : updates \\ \\UCUpdates.cab en exécutant l’une des cmdlets suivantes :
    
      - Si le fichier .cab se trouve sur le même ordinateur que celui qui exécute le service à mettre à jour (service:Redmond-websvc-2), exécutez l’applet de commande suivante :
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-2 -FileName C:\Updates\UCUpdates.cab
    
      - Si le fichier .cab se trouve sur un autre ordinateur que celui qui exécute le service à mettre à jour (service:Redmond-websvc-3), exécutez l’applet de commande suivante :
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-3 -ByteInput C:\Updates\UCUpdates.cab

4.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

5.  Dans la barre de navigation de gauche, cliquez sur **Clients**, puis sur **Mise à jour du périphérique**.

6.  Dans la page **Mise à jour du périphérique**, cliquez sur une mise à jour de la liste, puis effectuez l’une des opérations suivantes :
    
      - **Annulez une mise à jour en attente.** Pour empêcher le déploiement de la mise à jour sélectionnée vers les périphériques de votre entreprise, cliquez sur le menu **Action**, puis sur **Annuler les mises à jour en attente**.
    
      - **Approuvez une mise à jour.** Pour autoriser le déploiement de la mise à jour sélectionnée vers les périphériques de votre entreprise, cliquez sur le menu **Action**, puis sur **Approuver**.
    
      - **Restaurez une mise à jour.** Pour autoriser le déploiement d’une mise à jour approuvée vers les périphériques de votre entreprise, cliquez sur le menu **Action**, puis sur **Restaurer**.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Gestion des appareils, des téléphones et des applications clientes dans Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

