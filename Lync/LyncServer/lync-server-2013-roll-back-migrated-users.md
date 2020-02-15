---
title: 'Lync Server 2013 : restauration des utilisateurs migrés'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Roll back migrated users
ms:assetid: bfabaf0b-9a42-4057-b729-a7ab9eee8c72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205224(v=OCS.15)
ms:contentKeyID: 48185286
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7398e69e5a02924025d63fc48096244d67c49aeb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051468"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="roll-back-migrated-users-in-lync-server-2013"></a>Restaurer les utilisateurs migrés dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-07_

Si vous devez restaurer la fonctionnalité magasin de contacts unifié, annulez les contacts uniquement si vous redéplacez l’utilisateur vers Exchange 2010 ou Lync Server 2010. Pour effectuer la restauration, désactivez la stratégie définie pour l’utilisateur, puis exécutez l’applet de commande **Invoke-CsUcsRollback**. Le fait de simplement exécuter **Invoke-CsUcsRollback** ne suffit pas à garantir une restauration permanente ; en effet, si la stratégie n’est pas désactivée, le magasin de contacts unifié continuera d’être transféré. Par exemple, si un utilisateur est annulé car Exchange 2013 est restauré vers Exchange 2010, puis la boîte aux lettres de l’utilisateur est déplacée vers Exchange 2013, la migration du magasin de contacts unifié est lancée à nouveau sept jours après la restauration, aussi longtemps que le magasin de contacts unifié est toujours activé pour l’utilisateur dans la stratégie de services d’utilisateurs.

<div>


> [!IMPORTANT]  
> L’applet de commande <STRONG>Move-Csuser</STRONG> restaure automatiquement le magasin de contacts de l’utilisateur à partir d’Exchange 2013 vers Lync Server 2013 dans les situations suivantes : 
> <UL>
> <LI>
> <P>Lorsque les utilisateurs sont déplacés de Lync Server 2013 vers Lync Server 2010.</P>
> <LI>
> <P>Lorsque les utilisateurs sont migrés sur des sites distants, par exemple lorsqu’un utilisateur est déplacé de Lync Online vers Lync Server 2013 local, ou vice versa.</P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> L’importation des données d’un magasin de contacts unifié à partir d’une base de données de sauvegarde peut endommager les données du magasin de contacts unifié et les données utilisateur si le mode de magasin de contacts unifié a été modifié entre l’exportation et l’importation. Par exemple : 
> <UL>
> <LI>
> <P>Si vous exportez des listes de contacts avant la migration des contacts des utilisateurs vers Exchange 2013 puis, après la migration, importez les mêmes données, les données du magasin de contacts unifié et les listes de contacts sont endommagées.</P>
> <LI>
> <P>Si vous exportez les données UserData après avoir migré les utilisateurs vers Exchange 2013, restaurez la migration, puis, pour une raison quelconque, vous importez les données à partir de après la migration, les données du magasin de contacts unifié et les listes de contacts sont endommagées.</P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> Avant de déplacer une boîte aux lettres Exchange d’Exchange 2013 vers Exchange 2010, l’administrateur Exchange doit s’assurer que l’administrateur de Lync Server a d’abord restauré les contacts de l’utilisateur Lync Server d’Exchange 2013 vers Lync Server. Pour restaurer les contacts du magasin de contacts unifié vers Lync Server, voir procédure « pour restaurer les contacts de magasin de contacts unifiés à partir d’Exchange 2013 vers Lync Server 2013 », plus loin dans cette section.



</div>

La procédure suivante explique comment restaurer les contacts des utilisateurs. Si vous utilisez l’applet de commande **Move-Csuser** pour déplacer des utilisateurs entre lync Server 2013 et lync Server 2010, vous pouvez ignorer ces étapes car l’applet de commande **Move-Csuser** annule automatiquement Unifed magasin de contacts lorsqu’il déplace les utilisateurs de Lync Server 2013 vers Lync Server 2010. **Move-Csuser** ne désactive pas la stratégie de magasin de contacts unifiée, de sorte que la migration vers le magasin de contacts unifié se répétera si l’utilisateur est ramené à Lync Server 2013.

<div>

## <a name="to-roll-back-user-contacts-from-lync-server-2013-to-lync-server-2010"></a>Pour restaurer les contacts utilisateur de Lync Server 2013 vers Lync Server 2010

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

2.  Désactivez le magasin de contacts unifié des utilisateurs à restaurer afin que ces derniers ne soient pas de nouveau transférés après la restauration. (Effectuez cette étape uniquement si vous souhaitez empêcher tout transfert ultérieure des utilisateurs.) Pour désactiver le magasin de contacts unifié d’utilisateurs spécifiques, sur la ligne de commande, tapez :
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    Par exemple :
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  Avant de transférer un utilisateur de Lync Server 2013 vers Lync Server 2010, restaurez la liste de contacts pour les utilisateurs spécifiés sur Lync Server.
    
    <div>
    

    > [!IMPORTANT]  
    > Si cette étape est omise, la liste de contacts sera perdue.

    
    </div>

4.  Restaurez les utilisateurs spécifiés. Sur la ligne de commande, tapez :
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    Par exemple :
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > Nous vous recommandons de ne pas utiliser l’option –Force pour forcer la restauration. Si vous le faites, les contacts des utilisateurs seront perdus.

    
    </div>

</div>

<div>

## <a name="to-roll-back-unified-contact-store-contacts-from-exchange-2013-to-lync-server-2013"></a>Pour restaurer les contacts du magasin de contacts unifié de Microsoft Exchange 2013 vers Lync Server 2013

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

2.  Désactivez le magasin de contacts unifié des utilisateurs à restaurer afin que ces derniers ne soient pas de nouveau transférés après la restauration. Pour désactiver le magasin de contacts unifié d’utilisateurs spécifiques, sur la ligne de commande, tapez :
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    Par exemple :
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  Restaurez les utilisateurs spécifiés. Sur la ligne de commande, tapez :
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    Par exemple :
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > Vous devez d’abord restaurer l’utilisateur Lync Server, puis déplacer la boîte aux lettres Exchange 2013. L’administrateur Exchange ne peut pas restaurer Exchange tant que la restauration de Lync Server n’est pas terminée. Nous vous recommandons de ne pas utiliser l’option –Force pour forcer la restauration. Si vous le faites, les contacts des utilisateurs seront perdus.

    
    </div>

4.  Une fois que vous avez restauré l’utilisateur sur Lync Server, l’administrateur Exchange peut restaurer l’utilisateur Exchange à partir d’Exchange 2013 vers Exchange 2010.

</div>

</div>

<span> </span>

</div>

</div>

</div>

