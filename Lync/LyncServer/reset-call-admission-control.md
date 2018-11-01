---
title: Réinitialisation du contrôle d’admission des appels
TOCTitle: Réinitialisation du contrôle d’admission des appels
ms:assetid: 5873f56c-f3d6-4d73-beea-c9f37d5077f6
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688064(v=OCS.15)
ms:contentKeyID: 49891360
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Réinitialisation du contrôle d’admission des appels

 

_**Dernière rubrique modifiée :** 2012-10-11_

Si un pool de serveurs frontauxLync Server 2010 héberge le service Contrôle d’admission des appels, vous devez transférer l’hébergement du service Contrôle d’admission des appels vers un pool Lync Server 2013 pour pouvoir supprimer le pool de serveurs frontauxLync Server 2010.

## Pour réinitialiser le service Contrôle d’admission des appels

1.  Ouvrez le Générateur de topologie.

2.  Cliquez avec le bouton droit sur le nœud du site, puis cliquez sur **Modifier les propriétés** .

3.  Sous **Définition du contrôle d’admission des appels** , assurez-vous que l’option **Activer le contrôle d’admission des appels** est sélectionnée.

4.  Sous **Pool frontal pour exécuter le contrôle d’admission des appels (CAC)** , sélectionnez le pool Lync Server 2013 qui doit héberger le service Contrôle d’admission des appels, puis cliquez sur **OK** .

5.  Publiez la topologie.

