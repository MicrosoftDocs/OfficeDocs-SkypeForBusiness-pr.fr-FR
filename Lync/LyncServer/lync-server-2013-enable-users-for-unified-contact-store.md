---
title: "Lync Server 2013 : Activ. des utilisateurs pour le magasin de contacts unifié"
TOCTitle: Activation des utilisateurs pour le magasin de contacts unifié
ms:assetid: 7b46a01f-beb5-4a33-adb0-35f0502b168d
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205024(v=OCS.15)
ms:contentKeyID: 49297828
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Activation des utilisateurs pour le magasin de contacts unifié dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-07_

Quand vous déployez Lync Server 2013 et publiez la topologie, le magasin de contact unifié est activé pour tous les utilisateurs par défaut. Vous n’avez pas besoin d’effectuer des actions supplémentaires pour activer le magasin de contact unifié après le déploiement de Lync Server 2013. Cependant, vous pouvez utiliser l’applet de commande **Set-CsUserServicesPolicy** pour personnaliser les utilisateurs pour lesquels le magasin de contact unifié est disponible. Vous pouvez activer cette fonctionnalité globalement, par site, par locataire, par personne ou par groupes de personnes.

## Pour activer les utilisateurs pour le magasin de contact unifié

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Effectuez l’une des opérations suivantes :
    
      - Pour activer le magasin de contact unifié globalement pour tous les utilisateurs Lync Server, dans la ligne de commande, tapez :
        
            Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
    
      - Pour activer le magasin de contact unifié pour tous les utilisateurs d’un site spécifique, dans la ligne de commande, tapez :
        
            New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
        
        Exemple :
        
            New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
    
      - Pour activer le magasin de contact unifié par locataire, dans la ligne de commande, tapez :
        
            Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
        
        Exemple :
        
            Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
    
      - Pour activer le magasin de contact unifié pour des utilisateurs spécifiques, dans la ligne de commande, tapez :
        
            New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
        
        > [!NOTE]  
        > Vous pouvez également utiliser un alias utilisateur ou un URI SIP à la place du nom d’affichage de l’utilisateur.        
        Exemple :
        
            New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
        
        > [!NOTE]  
        > Dans l’exemple précédant, la première commande crée une nouvelle stratégie par utilisateur appelée <em>Utilisateurs UCS activés</em> avec l’indicateur UcsAllowed défini à True. La seconde commande affecte la stratégie à l’utilisateur avec le nom complet Ken Myer, ce qui signifie que Ken Myer est désormais activé pour le magasin de contact unifié.
