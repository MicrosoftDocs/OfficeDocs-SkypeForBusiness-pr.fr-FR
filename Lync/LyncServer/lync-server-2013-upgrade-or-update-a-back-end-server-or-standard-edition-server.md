---
title: Mettre à niveau ou mettre à jour un serveur principal ou un serveur Standard Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Upgrade or update a Back End Server or Standard Edition server
ms:assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721942(v=OCS.15)
ms:contentKeyID: 49733879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd3617098c42cd38e9928f055a6348a7bf2f9342
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193077"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="upgrade-or-update-a-back-end-server-or-standard-edition-server-in-lync-server-2013"></a>Mise à niveau ou mise à jour d’un serveur principal ou d’un serveur Standard Edition dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Cette rubrique explique comment installer une mise à jour sur un serveur principal Enterprise Edition ou un serveur Standard Edition.

Si un serveur principal est arrêté durant au moins 30 minutes lors de sa mise à niveau, les utilisateurs peuvent être placés en mode Résilience. Lorsque la mise à mise à niveau est terminée et que les serveurs principaux sont encore connectés aux serveurs frontaux du pool, les utilisateurs repassent en fonctionnalité complète. Si la mise à niveau dure moins de 30 minutes, les utilisateurs ne seront pas affectés.

<div>

## <a name="to-update-a-back-end-server-or-standard-edition-server"></a>Pour mettre à jour un serveur principal ou un serveur Standard Edition

1.  Connectez-vous au serveur que vous mettez à niveau en tant que membre du rôle CsAdministrator.

2.  Téléchargez la mise à jour et extrayez-la sur le disque dur local.

3.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

4.  Arrêtez les services Lync Server. À partir de la ligne de commande, tapez :
    
        Stop-CsWindowsService

5.  Arrêtez les services World Wide Web. À partir de la ligne de commande, tapez :
    
        net stop w3svc

6.  Fermez toutes les fenêtres Lync Server Management Shell.

7.  Installez la mise à jour.

8.  Démarrez Lync Server Management Shell : Cliquez sur **Démarrer**, sur **Tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

9.  Arrêtez de nouveau les services Lync Server pour rattraper les assemblys mis dans le Global Assembly Cache (GAC). À partir de la ligne de commande, tapez :
    
        Stop-CsWindowsService

10. Redémarrez les services World Wide Web. À partir de la ligne de commande, tapez :
    
        net start w3svc

11. Appliquez les modifications apportées par LyncServerUpdateInstaller.exe sur les bases de données SQL Server en effectuant l’une des opérations suivantes :
    
      - S’il s’agit d’un serveur principal Enterprise Edition et qu’il n’y a pas de base de données colocalisée sur ce serveur, comme les bases de données d’archivage ou de surveillance, tapez ce qui suit dans la ligne de commande :
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    
      - S’il s’agit d’un serveur principal Enterprise Edition et qu’il existe des bases de données colocalisées sur ce serveur, tapez ce qui suit dans la ligne de commande :
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    
      - S’il s’agit d’un serveur Standard Edition, tapez ce qui suit dans la ligne de commande :
        
            Install-CsDatabase -Update -LocalDatabases

</div>

</div>

<span> </span>

</div>

</div>

</div>

