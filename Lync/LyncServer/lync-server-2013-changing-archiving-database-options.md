---
title: 'Lync Server 2013 : modification des options de base de données d’archivage'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changing Archiving database options
ms:assetid: 3775f09d-65b0-48bc-8a4d-d97bd0c3423c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204814(v=OCS.15)
ms:contentKeyID: 48183879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a820ca891ceb8196f8b4e0d2e023799f36e9e9ca
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190387"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changing-archiving-database-options-in-lync-server-2013"></a>Modification des options de base de données d’archivage dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Si vous déployez l’archivage à l’aide du stockage SQL Server pour l’archivage du stockage pour l’un de vos utilisateurs, vous pouvez réaliser les modifications suivantes au stockage de la base de données :

  - Utiliser une autre base de données SQL Server pour l’archivage du stockage. Cela inclut la base de données d’archivage principale et toute base de données que vous utilisez pour la mise en miroir SQL Server.

  - Basculez vers l’intégration de Microsoft Exchange pour stocker les données d’archivage et les fichiers sur les serveurs Exchange 2013. Si tous vos utilisateurs sont hébergés sur vos serveurs Exchange 2013 et que vous souhaitez utiliser le stockage Microsoft Exchange pour tous les utilisateurs de votre déploiement, vous devez supprimer les bases de données du magasin SQL Server de votre topologie.

Pour effectuer l’une ou l’autre de ces modifications, vous devez exécuter le générateur de topologie, effectuer les modifications, puis publier à nouveau la topologie. Pour ce faire, vous pouvez utiliser le générateur de topologie. Ne spécifiez pas le **magasin SQL Server d’archivage** ou activez les informations de **mise en miroir du magasin SQL Server** , sauf si vous avez des utilisateurs Lync qui ne sont pas hébergés sur des serveurs Exchange 2013.

<div>

## <a name="to-change-your-archiving-database-option"></a>Pour modifier vos options de base de données d’archivage

1.  Sur un ordinateur exécutant Lync Server 2013 ou sur lequel les outils d’administration Lync Server sont installés, ouvrez une session à l’aide d’un compte membre du groupe utilisateurs local (ou d’un compte doté de droits d’utilisateur équivalents).
    
    <div>
    

    > [!NOTE]  
    > Vous pouvez définir une topologie à l’aide d’un compte membre du groupe utilisateurs local, mais pour publier une topologie, qui est requise pour ajouter un composant à la topologie, vous devez utiliser un compte membre du groupe <STRONG>administrateurs du domaine</STRONG> et du groupe <STRONG>RTCUniversalServerAdmins</STRONG> et qui dispose des autorisations contrôle total (c’est-à-dire, lecture, écriture et modification) sur le partage de fichiers que vous utilisez pour le magasin de fichiers Lync Server 2013 (de sorte que le générateur de topologies puisse configurer les listes de contrôle d’accès discrétionnaire requises ( DACL) ou un compte disposant de droits équivalents.

    
    </div>

2.  Démarrez le Générateur de topologie.

3.  Dans l’arborescence de la console, accédez au pool de serveurs frontaux dans lequel vous avez déployé l’archivage, puis cliquez sur le nom du pool de serveurs frontaux dans lequel vous voulez modifier les options de base de données.

4.  Dans le menu **Action**, cliquez sur **Modifier les propriétés**.

5.  Dans la boîte de dialogue **Modifier les propriétés**, cliquez sur **Général**.

6.  Faites défiler la liste jusqu’à **Archivage**.

7.  Dans **Archivage**, procédez comme suit :
    
      - Pour choisir un autre magasin SQL Server existant, sous **Magasin SQL Server d’archivage**, dans la zone de liste déroulante, procédez comme suit :
        
          - Pour utiliser un magasin SQL Server existant, dans la zone de liste déroulante, cliquez sur le nom du magasin SQL Server que vous voulez utiliser.
        
          - Pour spécifier un nouveau magasin SQL Server, cliquez sur **Nouveau**, puis dans la boîte de dialogue **Définir un nouveau magasin SQL Server**, procédez comme suit :
            
              - Pour utiliser un magasin SQL Server existant, dans la zone de liste déroulante, cliquez sur le nom du magasin SQL Server que vous voulez utiliser.
            
              - Pour spécifier un nouveau magasin SQL Server, cliquez sur **nouveau**, puis dans la boîte de dialogue **définir un nouveau magasin SQL Server** , procédez comme suit :
                
                  - Dans **nom de domaine complet SQL Server**, spécifiez le nom de domaine complet (FQDN) du serveur sur lequel vous souhaitez créer le nouveau magasin SQL Server.
                
                  - Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou, pour définir une instance différente, cliquez sur **Instance nommée** et spécifiez l’instance à utiliser.
                
                  - Si l’instance SQL Server spécifiée se trouve dans une relation de mise en miroir, activez la case à cocher **cette instance SQL est dans la relation de mise en miroir** , puis, dans **numéro de port miroir**, spécifiez le numéro de port.
    
      - Pour ajouter le magasin SQL Server ou choisir un autre magasin SQL Server existant pour la mise en miroir, sélectionnez **Activer la mise en miroir du magasin SQL Server**, puis procédez comme suit :
        
          - Pour utiliser un magasin SQL Server existant pour la mise en miroir, dans la zone de liste déroulante **miroir du magasin SQL Server d’archivage** , cliquez sur le nom du magasin SQL Server que vous souhaitez utiliser pour la mise en miroir.
        
          - Pour spécifier un nouveau magasin SQL Server pour la mise en miroir, cliquez sur **nouveau**, puis dans la boîte de dialogue **définir un nouveau magasin SQL Server** , effectuez l’une des opérations suivantes :
            
            1.  Dans **nom de domaine complet SQL Server**, spécifiez le nom de domaine complet (FQDN) du serveur SQL Server sur lequel vous souhaitez créer le nouveau magasin SQL Server.
            
            2.  Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou sur **Instance nommée** pour définir une instance différente, puis spécifiez l’instance à utiliser.
            
            3.  Si l’instance SQL Server spécifiée se trouve dans une relation de mise en miroir, activez la case à cocher **cette instance SQL est dans la relation de mise en miroir** , puis, dans **numéro de port miroir**, spécifiez le numéro de port.
        
          - Si vous activez la mise en miroir SQL Server et que vous souhaitez ajouter ou modifier un témoin de mise en miroir SQL Server (une troisième instance de SQL Server qui peut détecter l’intégrité du serveur SQL Server et des instances miroir principales), activez la case à cocher **utiliser le témoin de mise en miroir SQL Server pour activer le basculement automatique** , puis effectuez l’une des opérations suivantes :
            
            1.  Dans **nom de domaine complet SQL Server**, spécifiez le nom de domaine complet du serveur sur lequel vous souhaitez créer le nouveau témoin de mise en miroir SQL Server.
            
            2.  Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou sur **Instance nommée** pour définir une instance différente, puis spécifiez l’instance à utiliser comme témoin de mise en miroir.
            
            3.  Si l’instance SQL Server spécifiée se trouve dans une relation de mise en miroir, activez la case à cocher **cette instance SQL est dans la relation de mise en miroir** , puis, dans **numéro de port miroir**, spécifiez le numéro de port.
    
      - Pour passer à l’intégration de Microsoft Exchange afin de stocker les données d’archivage et les fichiers sur les serveurs Exchange 2013 (si tous les utilisateurs de votre déploiement sont hébergés sur vos serveurs Exchange 2013), supprimez toutes les informations pour les bases de données d’archivage.
    
    <div>
    

    > [!IMPORTANT]  
    > Si vous avez des utilisateurs Lync qui ne sont pas hébergés sur des serveurs Exchange 2013, ne supprimez pas les informations du magasin SQL Server.

    
    </div>

8.  Pour enregistrer la configuration, cliquez sur **OK**.
    
    <div>
    

    > [!IMPORTANT]  
    > Les modifications que vous effectuez dans le générateur de topologie ne prennent effet que lorsque vous publiez la nouvelle topologie. Pour plus d’informations, reportez-vous <A href="lync-server-2013-publishing-the-updated-topology-to-add-archiving-databases.md">à la rubrique publication de la topologie mise à jour pour ajouter des bases de données d’archivage dans Lync Server 2013</A> dans la documentation de déploiement.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

