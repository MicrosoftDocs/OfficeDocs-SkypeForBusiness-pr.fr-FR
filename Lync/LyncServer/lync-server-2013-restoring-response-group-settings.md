---
title: Restauration des paramètres Response Group
TOCTitle: Restauration des paramètres Response Group
ms:assetid: 4f8e1949-925d-4538-be1d-9ac7c06b2aca
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Hh202174(v=OCS.15)
ms:contentKeyID: 53095419
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Restauration des paramètres Response Group

 

_**Dernière rubrique modifiée :** 2013-02-18_

Si vous avez déployé le application Response Group et que vous devez restaurer un serveur principal ou un serveur Standard Edition, vous devez également restaurer les paramètres de configuration du Response Group.

## Pour restaurer les paramètres de configuration du Response Group

1.  Sur la ligne de commande, tapez :
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<pool FQDN>" -OverwriteOwner -FileName "<path and file name of the backed up file at $Backup>"
    
    Par exemple :
    
        Import-CsRgsConfiguration -Destination "service: ApplicationServer:pool01.contoso.com" -OverwriteOwner -FileName "C:\RgsConfiguration.zip"

