---
title: Mise à niveau ou mise à jour d’un serveur principal ou d’un serveur Standard Edition Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Upgrade or update a Back End Server or Standard Edition server
ms:assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721942(v=OCS.15)
ms:contentKeyID: 49733879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b9d5ffba604ed5e32109ed5f1a2020b1e083b22
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846462"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="upgrade-or-update-a-back-end-server-or-standard-edition-server-in-lync-server-2013"></a>Mise à niveau ou mise à jour d’un serveur principal ou d’un serveur Standard Edition Server dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-11-01_

Cette rubrique explique comment installer une mise à jour sur un serveur principal Enterprise Edition ou un serveur Standard Edition Server.

Si un serveur principal est arrêté pendant au moins 30 minutes lors de la mise à niveau, les utilisateurs peuvent alors basculer en mode de résilience. Lorsque la mise à niveau est terminée et que les serveurs dorsaux sont à nouveau connectés avec les serveurs frontaux de la liste, les utilisateurs sont retournés à toutes les fonctionnalités. Si la mise à niveau dure moins de 30 minutes, les utilisateurs ne sont pas affectés.

<div>

## <a name="to-update-a-back-end-server-or-standard-edition-server"></a>Pour mettre à jour un serveur principal ou un serveur Standard Edition

1.  Connectez-vous au serveur que vous mettez à niveau en tant que membre du rôle CsAdministrator.

2.  Téléchargez la mise à jour et extrayez-la sur le disque dur local.

3.  Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

4.  Arrêtez les services Lync Server. À partir de la ligne de commande, tapez :
    
        Stop-CsWindowsService

5.  Arrêtez les services World Wide Web. À partir de la ligne de commande, tapez :
    
        net stop w3svc

6.  Fermez toutes les fenêtres de Lync Server Management Shell.

7.  Installez la mise à jour.

8.  Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

9.  Arrêtez de nouveau les services Lync Server pour détecter les assemblys du cache d’assembly global (GAC)-d À partir de la ligne de commande, tapez :
    
        Stop-CsWindowsService

10. Redémarrez les services World Wide Web. À partir de la ligne de commande, tapez :
    
        net start w3svc

11. Appliquez les modifications apportées par LyncServerUpdateInstaller. exe aux bases de données SQL Server en effectuant l’une des opérations suivantes:
    
      - S’il s’agit d’un serveur principal Enterprise Edition et qu’il n’y a pas de bases de données colocalisées sur ce serveur, telles que des bases de données d’archivage ou de surveillance, tapez les informations suivantes dans une ligne de commande:
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    
      - S’il s’agit d’une base de données serveur principal de la version Enterprise Edition et de bases de données colocalisées sur ce serveur, tapez les informations suivantes à partir de la ligne de commande suivante:
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    
      - S’il s’agit d’un serveur Standard Edition Server, tapez les informations suivantes dans une ligne de commande:
        
            Install-CsDatabase -Update -LocalDatabases

</div>

</div>

<span> </span>

</div>

</div>

</div>

