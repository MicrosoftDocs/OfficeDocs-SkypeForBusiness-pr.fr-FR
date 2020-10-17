---
title: 'Lync Server 2013 : affichage de l’état des services exécutés sur un ordinateur'
description: 'Lync Server 2013 : afficher l’état des services exécutés sur un ordinateur.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View the status of services running on a computer
ms:assetid: f41918e7-4c02-431e-840a-88a1f36ae499
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182606(v=OCS.15)
ms:contentKeyID: 48185804
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22aeb13f2beb5d3b0ee5eec8109eceeb14e40213
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571350"
---
# <a name="view-the-status-of-services-running-on-a-computer-in-lync-server-2013"></a>Affichage de l’état des services exécutés sur un ordinateur dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-22_

Vous pouvez utiliser le panneau de configuration Lync Server 2013 pour afficher tous les services en cours d’exécution sur un ordinateur spécifique dans votre topologie Lync Server et voir l’état de chaque service.

<div>

## <a name="to-view-the-status-of-services-running-on-a-computer"></a>Pour afficher l’état des services exécutés sur un ordinateur

1.  Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **topologie**.

4.  Sur la page **État** , triez ou recherchez la liste, selon vos besoins, pour trouver l’ordinateur qui vous intéresse, puis cliquez sur le nom de l’ordinateur.

5.  Effectuez l’une des opérations suivantes :
    
      - Pour afficher le dernier état des services en cours d’exécution sur l’ordinateur, cliquez sur **obtenir le statut du service**.
    
      - Pour afficher la liste des services spécifiques en cours d’exécution sur l’ordinateur et l’état de chaque service, cliquez sur **Propriétés**, puis sur **Fermer** pour revenir à la liste.

</div>

<div>

## <a name="viewing-service-status-by-using-windows-powershell-cmdlets"></a>Affichage de l’état du service à l’aide des applets de commande Windows PowerShell

Vous pouvez également afficher l’état du service à l’aide de Windows PowerShell et de la cmdlet **Get-CsWindowsService** . Vous pouvez exécuter cette applet de commande à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-view-service-status"></a>Pour afficher l’état du service

  - Pour afficher l’état du service sur un ordinateur, tapez une commande semblable à la suivante dans Lync Server Management Shell, puis appuyez sur entrée :
    
        Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
    
    Cette commande renvoie des informations comme celles-ci :
    
        RoleName                                  Status
        --------                                  ------
        {W3SVC}                                   Running
        {CentralManagement}                       Running
        {ClsAgent}                                Running
        {Registrar, UserServer, EdgeServer}       Running
        {ApplicationServer}                       Running
        {ConferencingServer}                      Running
        {MediationServer}                         Running

</div>

Pour plus d’informations, consultez la rubrique [Get-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/Get-CsWindowsService).

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

