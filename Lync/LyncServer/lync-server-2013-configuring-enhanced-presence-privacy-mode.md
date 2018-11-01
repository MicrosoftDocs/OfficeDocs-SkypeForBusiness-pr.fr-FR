---
title: Configuration du mode de confidentialité améliorée de la présence
TOCTitle: Configuration du mode de confidentialité améliorée de la présence
ms:assetid: e7a6b873-486d-4dfb-a967-c48f61f237f3
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg399028(v=OCS.15)
ms:contentKeyID: 49299174
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration du mode de confidentialité améliorée de la présence

 

_**Dernière rubrique modifiée :** 2016-12-08_

Grâce au mode de confidentialité améliorée de la présence, les utilisateurs peuvent limiter leurs informations de présence afin que seules les personnes figurant dans leur liste de contacts Lync 2013 puissent les consulter. Le paramètre EnablePrivacyMode des cmdlets **New-CsPrivacyConfiguration** et **Set-CsPrivacyConfiguration** contrôle cette option. Lorsque le paramètre EnablePrivacyMode est défini sur True, l’option permettant de limiter les informations de présence aux contacts apparaît dans les options de statut de Lync 2013. Lorsque l’option EnablePrivacyMode est définie sur False, les utilisateurs peuvent choisir de toujours autoriser les utilisateurs à consulter leurs informations de présence ou d’accepter toutes les futures modifications que l’administrateur apporte au mode de confidentialité.

> [!IMPORTANT]  
> Les paramètres de confidentialité Lync 2013 et Lync 2010 ne sont pas validés par les versions précédentes (Microsoft Office Communicator 2007 R2 ou Microsoft Office Communicator 2007). Si les versions précédentes d’Office Communicator sont autorisées à se connecter, le statut, les coordonnées ou l’image d’un utilisateur Lync 2013 peuvent être consultés par toute personne non autorisée. Par ailleurs, les paramètres de confidentialité d’un utilisateur Lync 2013 sont réinitialisés si cet utilisateur se connecte avec des versions précédentes de Communicator.<br />
Pour ces raisons, dans un scénario de migration, avant de pouvoir activer le mode de confidentialité améliorée de la présence :<ul>
> <li><p>Vérifiez que chaque utilisateur a installé Lync 2013.</p></li>
> <li><p>Définissez une règle de stratégie de version de client empêchant les versions précédentes de Communicator de se connecter.</p></li></ul>


## Pour activer le mode de confidentialité améliorée de la présence

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Exécutez la commande suivante :
    
        Get-CsPrivacyConfiguration | Set-CsPrivacyConfiguration -EnablePrivacyMode $True
    
    Cette commande active le mode confidentialité pour tous les paramètres de confidentialité utilisés actuellement dans votre entreprise.

## Voir aussi

#### Autres ressources

[Get-CsPrivacyConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsPrivacyConfiguration)  
[New-CsPrivacyConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsPrivacyConfiguration)  
[Set-CsPrivacyConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsPrivacyConfiguration)

