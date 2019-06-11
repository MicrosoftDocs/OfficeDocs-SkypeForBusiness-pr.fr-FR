---
title: 'Lync Server 2013 : Restauration des utilisateurs migrés'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Roll back migrated users
ms:assetid: bfabaf0b-9a42-4057-b729-a7ab9eee8c72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205224(v=OCS.15)
ms:contentKeyID: 48185286
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57462cee6c4996f0beb51290f8382a1736d3e635
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822439"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="roll-back-migrated-users-in-lync-server-2013"></a>Restauration des utilisateurs migrés dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-07_

Si vous avez besoin de restaurer la fonctionnalité de magasin de contacts unifiée, restaurez les contacts uniquement si vous revenez à l’utilisateur dans Exchange 2010 ou Lync Server 2010. Pour effectuer la restauration, désactivez la stratégie définie pour l’utilisateur, puis exécutez l’applet de commande **Invoke-CsUcsRollback**. La simple exécution de **Invoke-CsUcsRollback** ne suffit pas à garantir une restauration permanente ; en effet, si la stratégie n’est pas désactivée, le magasin de contacts unifié continue d’être transféré. Par exemple, si un utilisateur est restauré, car Exchange 2013 est restauré dans Exchange 2010, puis la boîte aux lettres de l’utilisateur est déplacée vers Exchange 2013, la migration de magasin de contacts unifiée sera lancée à nouveau après le Rollback, tant que magasin de contacts unifié est toujours activée pour l’utilisateur dans la stratégie de services des utilisateurs.

<div>


> [!IMPORTANT]  
> L’applet de commande <STRONG>Move-Csuser</STRONG> restaure automatiquement le magasin de contacts de l’utilisateur à partir d’Exchange 2013 vers Lync Server 2013 dans les situations suivantes: 
> <UL>
> <LI>
> <P>Lorsque les utilisateurs sont déplacés de Lync Server 2013 vers Lync Server 2010.</P>
> <LI>
> <P>Lorsque les utilisateurs migrent l’environnement croisé, par exemple lorsqu’un utilisateur est déplacé de Lync Online vers Lync Server 2013 local, ou vice-versa.</P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> L’importation des données d’un magasin de contacts unifié à partir d’une base de données de sauvegarde peut endommager les données du magasin de contacts unifié et les données utilisateur si le mode de magasin de contacts unifié a été modifié entre l’exportation et l’importation. Par exemple : 
> <UL>
> <LI>
> <P>Si vous exportez des listes de contacts avant la migration des contacts de l’utilisateur vers Exchange 2013, puis après la migration, vous importez les mêmes données, les données et les listes de contacts du magasin de contacts unifié seront corrompues.</P>
> <LI>
> <P>Si vous exportez des éléments UserData après avoir migré des utilisateurs vers Exchange 2013, restaurez la migration, et pour une raison quelconque, vous importez les données à partir d’après la migration, les données et les listes de contacts du magasin de contacts unifié seront endommagées.</P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> Avant de déplacer une boîte aux lettres Exchange à partir d’Exchange 2013 vers Exchange 2010, l’administrateur Exchange doit s’assurer que l’administrateur de Lync Server a restauré le premier contact de l’utilisateur du serveur Lync à partir d’Exchange 2013 sur Lync Server. Pour restaurer des contacts de magasin de contacts unifiés vers Lync Server, reportez-vous à la procédure «pour restaurer des contacts de magasin de contacts unifiés à partir d’Exchange 2013 vers Lync Server 2013», plus loin dans cette section.



</div>

La procédure suivante explique comment restaurer les contacts des utilisateurs. Si vous utilisez l’applet de méthode **Move-Csuser** pour déplacer des utilisateurs entre lync Server 2013 et lync Server 2010, vous pouvez ignorer ces étapes dans la mesure où l’applet de ligne de **déplacement-Csuser** annule automatiquement Unifed magasin de contacts lors du déplacement des utilisateurs de Lync Server 2013 vers Lync. Server 2010. **Move-Csuser** n’entraîne pas la désactivation de la stratégie de magasin de contacts unifiée, de sorte que la migration vers le magasin de contacts unifié se reproduit si l’utilisateur est reculé sur Lync Server 2013.

<div>

## <a name="to-roll-back-user-contacts-from-lync-server-2013-to-lync-server-2010"></a>Pour restaurer des contacts de l’utilisateur de Lync Server 2013 vers Lync Server 2010

1.  Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Désactivez le magasin de contacts unifié pour que les utilisateurs soient restaurés de façon à ce qu’ils ne soient pas à nouveau migrés après la restauration. (N’effectuez cette étape que si vous voulez vous assurer que les utilisateurs ne seront pas remigré ultérieurement.) Pour désactiver le magasin de contacts unifié pour des utilisateurs individuels, sur la ligne de commande, tapez:
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    Par exemple :
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  Avant de déplacer un utilisateur de Lync Server 2013 vers Lync Server 2010, restaurez la liste d’amis pour les utilisateurs spécifiés sur Lync Server.
    
    <div>
    

    > [!IMPORTANT]  
    > Si cette étape n’est pas spécifiée, la liste d’amis sera perdue.

    
    </div>

4.  Restaurez les utilisateurs spécifiés. Dans la ligne de commande, tapez :
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    Exemple :
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > Nous vous déconseillons d’utiliser l’option – force pour forcer la restauration. Si vous utilisez cette option, les contacts des utilisateurs seront perdus.

    
    </div>

</div>

<div>

## <a name="to-roll-back-unified-contact-store-contacts-from-exchange-2013-to-lync-server-2013"></a>Pour restaurer des contacts de magasin de contacts unifiés à partir d’Exchange 2013 vers Lync Server 2013

1.  Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Désactivez le magasin de contacts unifié pour que les utilisateurs soient restaurés de façon à ce qu’ils ne soient pas à nouveau migrés après la restauration. Pour désactiver le magasin de contacts unifié pour des utilisateurs individuels, sur la ligne de commande, tapez:
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    Par exemple :
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  Restaurez les utilisateurs spécifiés. Dans la ligne de commande, tapez :
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    Exemple :
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > Vous devez d’abord restaurer l’utilisateur de Lync Server, puis déplacer la boîte aux lettres Exchange 2013. L’administrateur Exchange ne peut pas restaurer Exchange tant que la restauration du serveur Lync n’est pas terminée. Nous vous déconseillons d’utiliser l’option – force pour forcer la restauration. Si vous utilisez cette option, les contacts des utilisateurs seront perdus.

    
    </div>

4.  Après la restauration de l’utilisateur sur Lync Server, l’administrateur Exchange peut restaurer l’utilisateur Exchange à partir d’Exchange 2013 vers Exchange 2010.

</div>

</div>

<span> </span>

</div>

</div>

</div>

