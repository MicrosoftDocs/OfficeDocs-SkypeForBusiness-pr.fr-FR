---
title: Publier la base de données d’emplacements
TOCTitle: Publier la base de données d’emplacements
ms:assetid: dd032b5b-df0e-4017-ac46-e17570c1ab1e
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398974(v=OCS.15)
ms:contentKeyID: 49299045
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Publier la base de données d’emplacements

 

_**Dernière rubrique modifiée :** 2012-10-30_

Le client ne pourra accéder aux nouveaux emplacements ajoutés à la base de données d’emplacements qu’une fois publiés.

Pour plus d’informations, voir la documentation de Lync Server Management Shell pour la cmdlet suivante :

  - **Publish-CsLisConfiguration**

Si vous utilisez des passerelles ELIN, vous devez également charger les numéros d’identification de l’emplacement en cas d’urgence dans la base de données d’identification automatique de l’emplacement (ALI, Automatic Location Identification) de votre opérateur RTC. Celui-ci peut exiger l’utilisation d’un format spécifique pour les enregistrements ELIN. Pour plus d’informations, contactez votre opérateur RTC. Vous pouvez exporter les enregistrements à partir de la base de données service d’informations sur l’emplacement et les mettre en forme, le cas échéant.

## Pour publier la base de données d’emplacements

  - Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

  - Exécutez la cmdlet suivante pour publier la base de données d’emplacements.
    
        Publish-CsLisConfiguration

