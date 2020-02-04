---
title: 'Lync Server 2013 : configuration requise pour le serveur de chat permanent'
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
ms.openlocfilehash: 0437f56c5eb5564eb4f85809aefd181c2cbd2eaf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746554"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-persistent-chat-server-in-lync-server-2013"></a>Configuration requise pour le serveur de chat permanent dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-01-06_

Chaque ordinateur qui héberge le serveur Chat permanent doit avoir accès à une topologie Lync Server 2013 existante avec les composants suivants :

  - **Serveur frontal Lync Server 2013.**  Le serveur frontal est le serveur principal pour le routage SIP (Session Initiation Protocol), qui permet de communiquer entre les ordinateurs exécutant le serveur Chat permanent et la fonctionnalité de conversation permanente possible. Avant de commencer à déployer le serveur de chat permanent, vérifiez le déploiement de Lync Server 2013 Standard Edition ou d’un pool frontal Lync Server et de tout autre ordinateur interne exécutant Lync Server, selon les besoins de votre organisation.

Les sections suivantes décrivent les conditions requises pour le serveur de chat permanent et la base de données qui stocke les données de chat permanent.

<div>

## <a name="persistent-chat-server-requirements"></a>Configuration requise pour le serveur de chat permanent

Pour plus d’informations sur le matériel recommandé pour le déploiement de Lync Server et la dernière version de Chat Server, voir [plates-formes matérielles pour Lync Server 2013](lync-server-2013-server-hardware-platforms.md) dans la documentation de support.

Pour plus d’informations sur la prise en charge des systèmes d’exploitation serveur et outils pour Lync Server et serveur de chat permanent, voir [prise en charge du système d’exploitation serveur et outils dans Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md) dans la documentation de support technique.

Pour plus d’informations sur les logiciels supplémentaires requis pour le déploiement d’un serveur de chat permanent, voir le tableau suivant.

### <a name="persistent-chat-server-software-prerequisites"></a>Conditions préalables pour le logiciel serveur Chat permanent

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
<td><p>Utilisé par le serveur de chat permanent et le service de conformité des conversations permanentes, s’il est déployé.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-database-requirements"></a>Exigences de base de données serveur de chat permanent

Le serveur Chat permanent utilise la base de données de chat permanent pour stocker les données de l’historique des conversations, de la configuration et de la mise en service des utilisateurs. Le cas échéant, elle utilise la base de données de conformité des conversations permanentes pour stocker les données de conformité.

<div>


> [!IMPORTANT]  
> La base de données de chat permanent (MGC) et la base de données de conformité (mgccomp) peuvent être localisées dans la même instance de SQL Server ou sur des serveurs SQL Server différents.



</div>

Pour préparer une plateforme de serveur de base de données, vérifiez que chaque ordinateur respecte la configuration matérielle requise, puis installez les logiciels prérequis.

La plateforme serveur pour les serveurs de base de données de chat permanent nécessite le même matériel que le serveur de base de données principal de Lync Server. Pour plus d’informations, reportez-vous à la rubrique [plateformes matérielles pour Lync server 2013](lync-server-2013-server-hardware-platforms.md) dans la documentation de support.

Sur le serveur de bases de données, vérifiez que l’une des applications logicielles suivantes est installée :

  - Microsoft SQL Server 2012. Pour plus d’informations sur l’installation de Microsoft SQL Server 2012, voir installer SQL Server 2012 [http://go.microsoft.com/fwlink/p/?LinkID=248559](http://go.microsoft.com/fwlink/p/?linkid=248559).

  - Microsoft SQL Server 2008 R2. Pour plus d’informations sur l’installation de Microsoft SQL Server 2008 R2, voir « installation de SQL Server (SQL Server 2008 R2 [http://go.microsoft.com/fwlink/?LinkId=275702](http://go.microsoft.com/fwlink/?linkid=275702)) » à l’adresse.

</div>

<div>

## <a name="persistent-chat-server-certificate-requirements"></a>Conditions requises pour le certificat serveur Chat permanent

Pour plus d’informations sur l’acquisition de certificats, la création de la base de données SQL Server et la création de magasins de fichiers, voir [déploiement de Lync Server 2013](lync-server-2013-deploying-lync-server.md) dans la documentation de déploiement.

</div>

</div>

<span> </span>

</div>

</div>

</div>

