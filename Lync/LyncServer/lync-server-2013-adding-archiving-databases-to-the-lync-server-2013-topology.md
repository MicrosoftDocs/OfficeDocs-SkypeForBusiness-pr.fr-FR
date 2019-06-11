---
title: 'Lync Server 2013: ajout de bases de données d’archivage à la topologie Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Adding Archiving databases to the Lync Server 2013 topology
ms:assetid: 089ab32f-1167-4bb8-a283-fdc6c9613072
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204654(v=OCS.15)
ms:contentKeyID: 48183338
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe77c57050d6d6c70d5818405fd657d5a8fd3f0e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838937"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-archiving-databases-to-the-lync-server-2013-topology"></a>Ajouter des bases de données d’archivage à la topologie Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-10_

Vous devez incorporer l’archivage dans votre topologie avant de configurer votre déploiement pour qu’il prenne en charge l’archivage. Les informations contenues dans cet article vous expliquent comment utiliser le générateur de topologie pour ajouter l’archivage à votre topologie existante.

<div>


> [!NOTE]  
> Si vous souhaitez utiliser l’intégration de Microsoft Exchange pour stocker les données et fichiers d’archivage sur les serveurs Exchange 2013 pour tous les utilisateurs de votre déploiement, ne spécifiez pas <STRONG>l’archivage de SQL Server Store</STRONG> ou n’utilisez pas les informations de <STRONG>mise en miroir SQL Server Store</STRONG> .



</div>

<div>

## <a name="to-add-archiving-database-support-to-your-topology"></a>Pour ajouter la prise en charge de la base de données d’archivage à votre topologie

1.  Sur un ordinateur exécutant Lync Server 2013 ou sur lequel sont installés les outils d’administration de Lync Server, connectez-vous à l’aide d’un compte qui est membre du groupe utilisateurs local (ou d’un compte disposant de droits d’utilisateur équivalents).
    
    <div>
    

    > [!NOTE]  
    > Vous pouvez définir une topologie à l’aide d’un compte membre du groupe utilisateurs locaux, mais pour publier une topologie, qui est nécessaire pour ajouter un serveur à la topologie, vous devez utiliser un compte membre du groupe <STRONG>administrateurs de domaine</STRONG> et de la <STRONG>RTCUniversalServer. </STRONG>Le groupe administrateurs et qui dispose des autorisations contrôle total (lecture, écriture et modification) sur le partage de fichiers que vous utilisez pour le magasin de fichiers 2013 de Lync Server (c’est-à-dire, afin que le générateur de topologie puisse configurer la liste de contrôle d’accès discrétionnaire requise (DACL) ou un compte disposant de droits équivalents.

    
    </div>

2.  Démarrer le générateur de topologie.

3.  Dans l’arborescence de la console, naviguez jusqu’au pool frontal dans lequel vous voulez déployer l’archivage, puis cliquez sur le nom du pool frontal pour lequel vous voulez déployer l’archivage.

4.  Dans le menu **Action**, cliquez sur **Modifier les propriétés**.

5.  Dans la boîte de dialogue **Modifier les propriétés**, cliquez sur **Général**.

6.  Faites défiler la liste jusqu’à **Archivage**.

7.  Activez la case à cocher **Archivage**.

8.  Sous **archivage de SQL Server Store,** effectuez l’une des opérations suivantes:
    
      - Pour utiliser un magasin SQL Server existant, dans la zone de liste déroulante, cliquez sur le nom du magasin SQL Server que vous voulez utiliser. Si tous vos utilisateurs sont hébergés sur Microsoft Exchange Server 2013 ou une version ultérieure, vous pouvez archiver les communications Lync pour tous vos utilisateurs dans Exchange. Dans ce cas, vous n’avez pas besoin de configurer le magasin SQL Server d’archivage.
    
      - Pour spécifier un nouveau SQL Server Store, cliquez sur **nouveau**puis, dans la boîte de dialogue **définir un nouveau SQL Server Store** , procédez comme suit:
        
          - Dans **FQDN SQL Server**, spécifiez le nom de domaine complet (FQDN) du serveur sur lequel vous souhaitez créer le nouveau SQL Server Store.
        
          - Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou, pour définir une instance différente, cliquez sur **Instance nommée** et spécifiez l’instance à utiliser.
        
          - Si l’instance SQL Server spécifiée se trouve dans une relation de mise en miroir, activez la case à cocher **cette instance SQL est dans une relation en miroir** , puis, dans numéro de port **en miroir**, spécifiez le numéro de port.

9.  Si vous souhaitez utiliser la mise en miroir SQL Server Store, sélectionnez **activer la mise en miroir SQL Server Store**, puis procédez comme suit:
    
      - Pour utiliser un magasin SQL Server existant pour la mise en miroir, dans la zone de liste déroulante archivage de **SQL Server Store** , cliquez sur le nom du magasin SQL Server que vous voulez utiliser pour la mise en miroir.
    
      - Pour spécifier un nouveau magasin SQL Server pour la mise en miroir, cliquez sur **nouveau**puis, dans la boîte de dialogue **définir un nouveau SQL Server Store** , effectuez l’une des opérations suivantes:
        
        1.  Dans **nom de domaine complet SQL Server**, spécifiez le nom de domaine complet (FQDN) du serveur SQL sur lequel vous souhaitez créer le nouveau SQL Server Store.
        
        2.  Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou, pour définir une instance différente, cliquez sur **Instance nommée** et spécifiez l’instance à utiliser.
        
        3.  Si l’instance SQL Server spécifiée se trouve dans une relation de mise en miroir, activez la case à cocher **cette instance SQL est dans une relation en miroir** , puis, dans numéro de port **en miroir**, spécifiez le numéro de port.
    
      - Si vous activez la mise en miroir SQL Server et souhaitez inclure un témoin de mise en miroir SQL Server (troisième instance SQL Server distincte capable de détecter l’état du serveur SQL Server principal et des instances de miroirs), sélectionnez le **témoin d’utilisation de miroirs SQL Server à activer. option de reprise automatique** , puis effectuez l’une des opérations suivantes:
        
        1.  Dans **FQDN SQL Server**, spécifiez le nom de domaine complet (FQDN) du serveur sur lequel vous souhaitez créer le nouveau témoin de mise en miroir SQL Server.
        
        2.  Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou sur **Instance nommée** pour définir une instance différente, puis spécifiez l’instance à utiliser comme témoin de mise en miroir.
        
        3.  Si l’instance SQL Server spécifiée se trouve dans une relation de mise en miroir, activez la case à cocher **cette instance SQL est dans une relation en miroir** , puis, dans numéro de port **en miroir**, spécifiez le numéro de port.

10. Pour enregistrer la configuration, cliquez sur **OK**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

