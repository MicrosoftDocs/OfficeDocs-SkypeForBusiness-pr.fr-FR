---
title: 'Lync Server 2013: affichage de l’état des services en cours d’exécution sur un ordinateur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View the status of services running on a computer
ms:assetid: f41918e7-4c02-431e-840a-88a1f36ae499
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182606(v=OCS.15)
ms:contentKeyID: 48185804
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52f7b1628f9e9fcd99eea84ebda2cbfe934fc7d6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846284"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-the-status-of-services-running-on-a-computer-in-lync-server-2013"></a>Afficher l’état des services en cours d’exécution sur un ordinateur dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-22_

Vous pouvez utiliser le panneau de configuration de Lync Server 2013 pour afficher tous les services en cours d’exécution sur un ordinateur spécifique dans la topologie de votre serveur Lync et afficher l’état de chaque service.

<div>

## <a name="to-view-the-status-of-services-running-on-a-computer"></a>Pour afficher l’état des services en cours d’exécution sur un ordinateur

1.  À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Topology**.

4.  Dans la page **État** , triez ou effectuez une recherche dans la liste, si nécessaire, pour trouver l’ordinateur qui vous intéresse, puis cliquez sur le nom de l’ordinateur.

5.  Effectuez l’une des opérations suivantes :
    
      - Pour afficher le dernier état des services en cours d’exécution sur l’ordinateur, cliquez sur **obtenir l’état du service**.
    
      - Pour afficher une liste de services spécifiques en cours d’exécution sur l’ordinateur et l’état de chaque service, cliquez sur **Propriétés**, puis sur **Fermer** pour revenir à la liste.

</div>

<div>

## <a name="viewing-service-status-by-using-windows-powershell-cmdlets"></a>Affichage de l’état du service à l’aide des cmdlets Windows PowerShell

Vous pouvez également afficher l’état du service à l’aide de Windows PowerShell et de l’applet **de connexion Get-CsWindowsService** . Vous pouvez exécuter cette applet de commande sur Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell «démarrage rapide: gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell».

<div>

## <a name="to-view-service-status"></a>Pour afficher l’état du service

  - Pour afficher l’état du service sur un ordinateur, tapez une commande similaire à celle qui suit dans Lync Server Management Shell, puis appuyez sur entrée:
    
        Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
    
    Cette commande renvoie le type d’informations suivant :
    
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


[Gestion des appareils, des téléphones et des applications client dans Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

