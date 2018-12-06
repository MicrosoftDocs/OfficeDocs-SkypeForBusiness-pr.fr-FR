---
title: 'Lync Server 2013 : Restauration des utilisateurs migrés'
TOCTitle: Restauration des utilisateurs migrés
ms:assetid: bfabaf0b-9a42-4057-b729-a7ab9eee8c72
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205224(v=OCS.15)
ms:contentKeyID: 49298730
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Restauration des utilisateurs migrés dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-07_

Si vous avez besoin de restaurer le magasin de contacts unifié, ne restaurez les contacts que si vous devez redéplacer l’utilisateur vers Exchange 2010 ou Lync Server 2010. Pour effectuer la restauration, désactivez la stratégie définie pour l’utilisateur, puis exécutez l’applet de commande **Invoke-CsUcsRollback**. La simple exécution de **Invoke-CsUcsRollback** ne suffit pas à garantir une restauration permanente ; en effet, si la stratégie n’est pas désactivée, le magasin de contacts unifié continuera d’être transféré. Si, par exemple, un utilisateur est restauré à la suite de la restauration de Exchange 2013 vers Exchange 2010, et que sa boîte aux lettres est ensuite déplacée vers Exchange 2013, le transfert du magasin de contacts unifié est relancée sept jours après la restauration, et ce tant que le magasin de contacts unifié reste activé pour cet utilisateur dans la stratégie des services d’utilisateurs.

> [!IMPORTANT]  
> L’applet de commande <strong>Move-CsUser</strong> restaure automatiquement le magasin de contacts d’un utilisateur de Exchange 2013 vers Lync Server 2013 dans les cas suivants :<ul>
> <li><p>lorsque des utilisateurs sont déplacés de Lync Server 2013 vers Lync Server 2010 ;</p></li>
> <li><p>lorsque des utilisateurs sont transférés d’un site à un autre, notamment quand un utilisateur est déplacé de Skype Entreprise Online vers un déploiement Lync Server 2013 sur site, ou inversement.</p></li></ul>


> [!IMPORTANT]  
> L’importation des données d’un magasin de contacts unifié à partir d’une base de données de sauvegarde peut endommager les données du magasin de contacts unifié et les données utilisateur si le mode de magasin de contacts unifié a été modifié entre l’exportation et l’importation. Par exemple :<ul>
> <li><p>Si vous exportez les listes de contacts avant que les contacts des utilisateurs soient transférés vers Exchange 2013 puis que vous importez les mêmes données une fois le transfert terminé, les données du magasin de contacts unifié et les listes de contacts sont endommagées.</p></li>
> <li><p>Si vous exportez les données utilisateur après avoir transféré les utilisateurs vers Exchange 2013, que vous restaurez le transfert, puis que vous importez les données après le transfert, les données du magasin de contacts unifié et les listes de contacts sont endommagées.</p></li></ul>


> [!IMPORTANT]  
> Avant de déplacer une boîte aux lettres Exchange de Exchange 2013 vers Exchange 2010, l’administrateur Exchange doit s’assurer que l’administrateur Lync Server a préalablement restauré les contacts des utilisateurs Lync Server de Exchange 2013 vers Lync Server. Pour restaurer les contacts du magasin de contacts unifié vers Lync Server, reportez-vous à la procédure « Pour restaurer les contacts du magasin de contacts unifié de Exchange 2013 vers Lync Server 2013 », dans la suite de cette section.

La procédure suivante explique comment restaurer les contacts des utilisateurs. Si vous exécutez l’applet de commande **Move-CsUser** pour déplacer les utilisateurs de Lync Server 2013 vers Lync Server 2010, vous pouvez ignorer ces étapes, car l’applet de commande **Move-CsUser** restaure automatiquement le magasin de contacts unifié en même temps qu’elle déplace les utilisateurs de Lync Server 2013 vers Lync Server 2010. Étant donné que l’applet de commande **Move-CsUser** ne désactive pas la stratégie du magasin de contacts unifié, le transfert de ce magasin recommencera si l’utilisateur est ultérieurement redéplacé vers Lync Server 2013.

## Pour restaurer les contacts des utilisateurs de Lync Server 2013 vers Lync Server 2010

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Désactivez le magasin de contacts unifié des utilisateurs à restaurer afin que ces derniers ne soient pas de nouveau transférés après la restauration. (Effectuez cette étape uniquement si vous souhaitez empêcher tout transfert ultérieure des utilisateurs.) Pour désactiver le magasin de contacts unifié d’utilisateurs spécifiques, dans la ligne de commande, tapez :
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    Exemple :
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  Avant de déplacer un utilisateur de Lync Server 2013 vers Lync Server 2010, restaurez la liste de contacts des utilisateurs spécifiés vers Lync Server.
    
    > [!IMPORTANT]  
    > Si cette étape est omise, la liste de contacts sera perdue.

4.  Restaurez les utilisateurs spécifiés. Dans la ligne de commande, tapez :
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    Exemple :
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    > [!IMPORTANT]  
    > Nous vous recommandons de ne pas utiliser l’option –Force pour forcer la restauration. Si vous le faites, les contacts des utilisateurs seront perdus.

## Pour restaurer les contacts du magasin de contacts unifié de Exchange 2013 vers Lync Server 2013

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Désactivez le magasin de contacts unifié des utilisateurs à restaurer afin que ces derniers ne soient pas de nouveau transférés après la restauration. Pour désactiver le magasin de contacts unifié d’utilisateurs spécifiques, dans la ligne de commande, tapez :
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    Exemple :
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  Restaurez les utilisateurs spécifiés. Dans la ligne de commande, tapez :
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    Exemple :
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    > [!IMPORTANT]  
    > Vous devez d’abord restaurer l’utilisateur Lync Server avant de déplacer sa boîte aux lettres Exchange 2013. L’administrateur Exchange ne peut pas restaurer Exchange tant que la restauration Lync Server n’est pas terminée. Nous vous recommandons de ne pas utiliser l’option –Force pour forcer la restauration. Si vous le faites, les contacts des utilisateurs seront perdus.

4.  Une fois que vous avez restauré l’utilisateur vers Lync Server, l’administrateur Exchange peut restaurer l’utilisateur Exchange de Exchange 2013 vers Exchange 2010.

