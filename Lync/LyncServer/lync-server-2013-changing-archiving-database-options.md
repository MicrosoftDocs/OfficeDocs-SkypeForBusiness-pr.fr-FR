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
ms.openlocfilehash: 198e2abff6118197167f0f017ace22fc2ad76381
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743484"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changing-archiving-database-options-in-lync-server-2013"></a>Modification des options de base de données d’archivage dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Si vous déployez l’archivage à l’aide du stockage SQL Server pour l’archivage pour l’un de vos utilisateurs, vous pouvez effectuer les modifications suivantes du stockage de la base de données :

  - Utilisez une autre base de données SQL Server pour l’archivage du stockage. Il s’agit de la base de données d’archivage principale et de la base de données que vous utilisez pour la mise en miroir SQL Server.

  - Basculez vers l’intégration de Microsoft Exchange pour stocker les données et fichiers d’archivage sur les serveurs Exchange 2013. Si tous vos utilisateurs sont sur votre serveur Exchange 2013 et que vous souhaitez utiliser le stockage Microsoft Exchange pour tous les utilisateurs de votre déploiement, vous devez supprimer les bases de données SQL Server Store de votre topologie.

Pour effectuer l’une de ces modifications, vous devez exécuter le générateur de topologie, apporter les modifications, puis publier de nouveau la topologie. Pour cela, vous pouvez utiliser le générateur de topologie. Ne spécifiez pas **l’archivage de SQL Server Store** ou activez les informations de **mise en miroir SQL Server Store** , sauf si vous avez des utilisateurs de Lync qui ne sont pas hébergés sur des serveurs Exchange 2013.

<div>

## <a name="to-change-your-archiving-database-option"></a>Pour modifier l’option de votre base de données d’archivage

1.  Sur un ordinateur exécutant Lync Server 2013 ou sur lequel sont installés les outils d’administration de Lync Server, connectez-vous à l’aide d’un compte qui est membre du groupe utilisateurs local (ou d’un compte disposant de droits d’utilisateur équivalents).
    
    <div>
    

    > [!NOTE]  
    > Vous pouvez définir une topologie à l’aide d’un compte membre du groupe utilisateurs locaux, mais pour publier une topologie, qui est nécessaire pour ajouter un composant à la topologie. vous devez utiliser un compte membre du groupe <STRONG>administrateurs de domaine</STRONG> et du groupe <STRONG>RTCUniversalServerAdmins</STRONG> et qui dispose des autorisations de contrôle total (en lecture, écriture et modification) sur le partage de fichiers que vous utilisez pour le magasin de fichiers 2013 Lync Server (c’est-à-dire que le générateur de topologie peut configurer les listes de contrôle d’accès discrétionnaire requises ( DACL ou un compte avec des droits équivalents.

    
    </div>

2.  Démarrer le générateur de topologie.

3.  Dans l’arborescence de la console, accédez au pool de serveurs frontaux dans lequel vous avez déployé l’archivage, puis cliquez sur le nom du pool de serveurs frontaux dans lequel vous voulez modifier les options de base de données.

4.  Dans le menu **Action**, cliquez sur **Modifier les propriétés**.

5.  Dans la boîte de dialogue **Modifier les propriétés**, cliquez sur **Général**.

6.  Faites défiler la liste jusqu’à **Archivage**.

7.  Dans **Archivage**, procédez comme suit :
    
      - Pour choisir un autre magasin SQL Server existant, sous **Magasin SQL Server d’archivage**, dans la zone de liste déroulante, procédez comme suit :
        
          - Pour utiliser un magasin SQL Server existant, dans la zone de liste déroulante, cliquez sur le nom du magasin SQL Server que vous voulez utiliser.
        
          - Pour spécifier un nouveau magasin SQL Server, cliquez sur **Nouveau**, puis dans la boîte de dialogue **Définir un nouveau magasin SQL Server**, procédez comme suit :
            
              - Pour utiliser un magasin SQL Server existant, dans la zone de liste déroulante, cliquez sur le nom du magasin SQL Server que vous voulez utiliser.
            
              - Pour spécifier un nouveau SQL Server Store, cliquez sur **nouveau**puis, dans la boîte de dialogue **définir un nouveau SQL Server Store** , procédez comme suit :
                
                  - Dans **FQDN SQL Server**, spécifiez le nom de domaine complet (FQDN) du serveur sur lequel vous souhaitez créer le nouveau SQL Server Store.
                
                  - Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou, pour définir une instance différente, cliquez sur **Instance nommée** et spécifiez l’instance à utiliser.
                
                  - Si l’instance SQL Server spécifiée se trouve dans une relation de mise en miroir, activez la case à cocher **cette instance SQL est dans une relation en miroir** , puis, dans numéro de port **en miroir**, spécifiez le numéro de port.
    
      - Pour ajouter le magasin SQL Server ou choisir un autre magasin SQL Server existant pour la mise en miroir, sélectionnez **Activer la mise en miroir du magasin SQL Server**, puis procédez comme suit :
        
          - Pour utiliser un magasin SQL Server existant pour la mise en miroir, dans la zone de liste déroulante **archivage de SQL Server Store** , cliquez sur le nom du magasin SQL Server que vous voulez utiliser pour la mise en miroir.
        
          - Pour spécifier un nouveau magasin SQL Server pour la mise en miroir, cliquez sur **nouveau**puis, dans la boîte de dialogue **définir un nouveau SQL Server Store** , effectuez l’une des opérations suivantes :
            
            1.  Dans **nom de domaine complet SQL Server**, spécifiez le nom de domaine complet (FQDN) du serveur SQL sur lequel vous souhaitez créer le nouveau SQL Server Store.
            
            2.  Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou, pour définir une instance différente, cliquez sur **Instance nommée** et spécifiez l’instance à utiliser.
            
            3.  Si l’instance SQL Server spécifiée se trouve dans une relation de mise en miroir, activez la case à cocher **cette instance SQL est dans une relation en miroir** , puis, dans numéro de port **en miroir**, spécifiez le numéro de port.
        
          - Si vous activez la mise en miroir SQL Server et voulez ajouter ou modifier un témoin de mise en miroir SQL Server (troisième instance SQL Server distincte capable de détecter l’état du serveur SQL Server principal et des instances miroir), activez la case à cocher **utiliser le témoin de mise en miroir SQL Server pour activer le basculement automatique** , puis effectuez l’une des opérations suivantes :
            
            1.  Dans **FQDN SQL Server**, spécifiez le nom de domaine complet (FQDN) du serveur sur lequel vous souhaitez créer le nouveau témoin de mise en miroir SQL Server.
            
            2.  Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou sur **Instance nommée** pour définir une instance différente, puis spécifiez l’instance à utiliser comme témoin de mise en miroir.
            
            3.  Si l’instance SQL Server spécifiée se trouve dans une relation de mise en miroir, activez la case à cocher **cette instance SQL est dans une relation en miroir** , puis, dans numéro de port **en miroir**, spécifiez le numéro de port.
    
      - Pour basculer vers l’intégration de Microsoft Exchange pour stocker les données et fichiers d’archivage sur les serveurs Exchange 2013 (si tous les utilisateurs de votre déploiement sont hébergés sur vos serveurs Exchange 2013), supprimez toutes les informations pour l’archivage des bases de données.
    
    <div>
    

    > [!IMPORTANT]  
    > Si vous avez des utilisateurs de Lync qui ne sont pas hébergés sur des serveurs Exchange 2013, ne supprimez pas les informations du Windows Store SQL Server.

    
    </div>

8.  Pour enregistrer la configuration, cliquez sur **OK**.
    
    <div>
    

    > [!IMPORTANT]  
    > Les modifications que vous apportez dans le générateur de topologie ne s’appliquent pas tant que vous n’avez pas publié la nouvelle topologie. Pour plus d’informations, reportez-vous <A href="lync-server-2013-publishing-the-updated-topology-to-add-archiving-databases.md">à la rubrique publication de la topologie mise à jour pour ajouter des bases de données d’archivage dans Lync Server 2013</A> dans la documentation de déploiement.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

