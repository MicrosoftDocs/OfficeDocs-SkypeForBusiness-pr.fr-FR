---
title: 'Lync Server 2013 : ajout de bases de données d’archivage à la topologie Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding Archiving databases to the Lync Server 2013 topology
ms:assetid: 089ab32f-1167-4bb8-a283-fdc6c9613072
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204654(v=OCS.15)
ms:contentKeyID: 48183338
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e73fe49aaf3a5b90a23bcfd6b99c9a5bb4476513
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008790"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-archiving-databases-to-the-lync-server-2013-topology"></a>Ajout de bases de données d’archivage à la topologie Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-10_

Vous devez incorporer l’archivage dans votre topologie avant de configurer votre déploiement pour qu’il prenne en charge l’archivage. Les informations contenues dans cette rubrique expliquent comment utiliser le générateur de topologie pour ajouter l’archivage à votre topologie existante.

<div>


> [!NOTE]  
> Si vous souhaitez utiliser l’intégration de Microsoft Exchange pour stocker les données d’archivage et les fichiers sur les serveurs Exchange 2013 pour tous les utilisateurs de votre déploiement, ne spécifiez pas le <STRONG>magasin SQL Server d’archivage</STRONG> ou n’utilisez pas les informations de <STRONG>mise en miroir du magasin SQL Server</STRONG> .



</div>

<div>

## <a name="to-add-archiving-database-support-to-your-topology"></a>Pour ajouter la prise en charge de la base de données d’archivage à votre topologie

1.  Sur un ordinateur exécutant Lync Server 2013 ou sur lequel les outils d’administration Lync Server sont installés, ouvrez une session à l’aide d’un compte membre du groupe utilisateurs local (ou d’un compte doté de droits d’utilisateur équivalents).
    
    <div>
    

    > [!NOTE]  
    > Vous pouvez définir une topologie à l’aide d’un compte membre du groupe utilisateurs local, mais pour publier une topologie, qui est requise pour ajouter un serveur à la topologie, vous devez utiliser un compte membre du groupe <STRONG>administrateurs du domaine</STRONG> et du groupe <STRONG>RTCUniversalServerAdmins</STRONG> et qui dispose des autorisations contrôle total (c’est-à-dire, lecture, écriture et modification) sur le partage de fichiers que vous utilisez pour le magasin de fichiers Lync Server 2013 (de sorte que le générateur de topologies puisse configurer la liste de contrôle d’accès discrétionnaire requise ou un compte disposant de droits équivalents.

    
    </div>

2.  Démarrez le Générateur de topologie.

3.  Dans l’arborescence de la console, accédez au pool frontal dans lequel vous voulez déployer l’archivage, puis cliquez sur le nom de ce pool frontal.

4.  Dans le menu **Action**, cliquez sur **Modifier les propriétés**.

5.  Dans la boîte de dialogue **Modifier les propriétés**, cliquez sur **Général**.

6.  Faites défiler la liste jusqu’à **Archivage**.

7.  Activez la case à cocher **Archivage**.

8.  Sous **magasin SQL Server d’archivage,** effectuez l’une des opérations suivantes :
    
      - Pour utiliser un magasin SQL Server existant, dans la zone de liste déroulante, cliquez sur le nom du magasin SQL Server que vous voulez utiliser. Si tous vos utilisateurs sont hébergés sur Microsoft Exchange Server 2013 ou version ultérieure, vous pouvez archiver les communications Lync pour tous vos utilisateurs dans Exchange. Dans ce cas, vous n’avez pas besoin de configurer le magasin d’archivage SQL Server.
    
      - Pour spécifier un nouveau magasin SQL Server, cliquez sur **nouveau**, puis dans la boîte de dialogue **définir un nouveau magasin SQL Server** , procédez comme suit :
        
          - Dans **nom de domaine complet SQL Server**, spécifiez le nom de domaine complet (FQDN) du serveur sur lequel vous souhaitez créer le nouveau magasin SQL Server.
        
          - Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou, pour définir une instance différente, cliquez sur **Instance nommée** et spécifiez l’instance à utiliser.
        
          - Si l’instance SQL Server spécifiée se trouve dans une relation de mise en miroir, activez la case à cocher **cette instance SQL est dans la relation de mise en miroir** , puis, dans **numéro de port miroir**, spécifiez le numéro de port.

9.  Si vous souhaitez utiliser la mise en miroir du magasin SQL Server, sélectionnez **activer la mise en miroir du magasin SQL Server**, puis procédez comme suit :
    
      - Pour utiliser un magasin SQL Server existant pour la mise en miroir, dans la zone de liste déroulante **miroir du magasin SQL Server d’archivage** , cliquez sur le nom du magasin SQL Server que vous souhaitez utiliser pour la mise en miroir.
    
      - Pour spécifier un nouveau magasin SQL Server pour la mise en miroir, cliquez sur **nouveau**, puis dans la boîte de dialogue **définir un nouveau magasin SQL Server** , effectuez l’une des opérations suivantes :
        
        1.  Dans **nom de domaine complet SQL Server**, spécifiez le nom de domaine complet (FQDN) du serveur SQL Server sur lequel vous souhaitez créer le nouveau magasin SQL Server.
        
        2.  Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou sur **Instance nommée** pour définir une instance différente, puis spécifiez l’instance à utiliser.
        
        3.  Si l’instance SQL Server spécifiée se trouve dans une relation de mise en miroir, activez la case à cocher **cette instance SQL est dans la relation de mise en miroir** , puis, dans **numéro de port miroir**, spécifiez le numéro de port.
    
      - Si vous activez la mise en miroir SQL Server et que vous souhaitez inclure un témoin de mise en miroir SQL Server (une troisième instance SQL Server distincte qui peut détecter l’intégrité du serveur SQL Server et des instances miroir principales), activez la case à cocher **utiliser le témoin de mise en miroir SQL Server pour activer le basculement automatique** , puis effectuez l’une des opérations suivantes :
        
        1.  Dans **nom de domaine complet SQL Server**, spécifiez le nom de domaine complet du serveur sur lequel vous souhaitez créer le nouveau témoin de mise en miroir SQL Server.
        
        2.  Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou sur **Instance nommée** pour définir une instance différente, puis spécifiez l’instance à utiliser comme témoin de mise en miroir.
        
        3.  Si l’instance SQL Server spécifiée se trouve dans une relation de mise en miroir, activez la case à cocher **cette instance SQL est dans la relation de mise en miroir** , puis, dans **numéro de port miroir**, spécifiez le numéro de port.

10. Pour enregistrer la configuration, cliquez sur **OK**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

