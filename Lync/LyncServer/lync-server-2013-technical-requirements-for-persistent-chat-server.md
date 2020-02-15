---
title: 'Lync Server 2013 : configuration technique requise pour le serveur de conversation permanente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Persistent Chat Server
ms:assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398495(v=OCS.15)
ms:contentKeyID: 48184383
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba8e3e02efeddc1229d3616c0cdcaf4ca241bf24
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42024405"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-persistent-chat-server-in-lync-server-2013"></a>Configuration technique requise pour le serveur de conversation permanente dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-01-06_

Chaque ordinateur qui héberge le serveur de conversation permanente doit avoir accès à une topologie Lync Server 2013 existante avec les composants suivants :

  - **Lync Server 2013, serveur frontal.**  Le serveur frontal est la base du routage SIP (Session Initiation Protocol), qui rend possible la communication entre les ordinateurs exécutant le serveur de conversation permanente et la fonctionnalité de conversation permanente. Avant de commencer à déployer le serveur de conversation permanente, vérifiez le déploiement de Lync Server 2013, Standard Edition ou d’un pool frontal Lync Server et de tous les autres ordinateurs internes exécutant Lync Server, selon les besoins de votre organisation.

Les sections suivantes décrivent les conditions requises spécifiques pour le serveur de conversation permanente et la base de données qui stocke les données de conversation permanente.

<div>

## <a name="persistent-chat-server-requirements"></a>Configuration requise pour le serveur de conversation permanente

Pour plus d’informations sur le matériel recommandé pour le déploiement de Lync Server et la dernière version du serveur de conversation permanente, voir [Server Hardware Platforms for Lync server 2013](lync-server-2013-server-hardware-platforms.md) dans la documentation de prise en charge.

Pour plus d’informations sur le serveur et les outils pris en charge par le système d’exploitation pour Lync Server et le serveur de conversation permanente, voir [serveur et outils pris en charge dans Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md) dans la documentation de prise en charge.

Pour plus d’informations sur les logiciels supplémentaires requis pour le déploiement du serveur de conversation permanente, consultez le tableau suivant.

### <a name="persistent-chat-server-software-prerequisites"></a>Configuration logicielle requise pour le serveur de conversation permanente

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Logiciels</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Message Queuing</p></td>
<td><p>Utilisé par le serveur de conversation permanente et le service de conformité de conversation permanente, s’il est déployé.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-database-requirements"></a>Configuration requise pour la base de données de serveur de conversation permanente

Le serveur de conversation permanente utilise la base de données de conversation permanente pour stocker les données d’historique, de configuration et de mise en service de l’utilisateur. Il utilise éventuellement la base de données de conformité de la conversation permanente pour stocker les données de conformité.

<div>


> [!IMPORTANT]  
> La base de données de conversation permanente (MGC) et la base de données de conformité (mgccomp) peuvent se trouver dans la même instance de SQL Server ou sur des serveurs SQL différents.



</div>

Pour préparer une plateforme de serveur de base de données, assurez-vous que chaque ordinateur répond à la configuration matérielle requise, puis installez les logiciels prérequis.

La plateforme de serveur pour les serveurs de bases de données de conversation permanente nécessite le même matériel que le serveur de base de données principal Lync Server. Pour plus d’informations, reportez-vous à la rubrique [Server Hardware Platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) dans la documentation de prise en charge.

Sur le serveur de base de données, assurez-vous que l’une des applications logicielles suivantes est installée :

  - Microsoft SQL Server 2012. Pour plus d’informations sur l’installation de Microsoft SQL Server 2012, voir « installer SQL Server 2012 [http://go.microsoft.com/fwlink/p/?LinkID=248559](http://go.microsoft.com/fwlink/p/?linkid=248559)» à l’adresse suivante :.

  - Microsoft SQL Server 2008 R2. Pour plus d’informations sur l’installation de Microsoft SQL Server 2008 R2, voir « installation de SQL Server (SQL Server 2008 R2 [http://go.microsoft.com/fwlink/?LinkId=275702](http://go.microsoft.com/fwlink/?linkid=275702)) » à l’adresse.

</div>

<div>

## <a name="persistent-chat-server-certificate-requirements"></a>Conditions requises pour les certificats de serveur de conversation permanente

Pour plus d’informations sur l’acquisition de certificats, la création de la base de données SQL Server et la création de magasins de fichiers, voir [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) dans la documentation de déploiement.

</div>

</div>

<span> </span>

</div>

</div>

</div>

