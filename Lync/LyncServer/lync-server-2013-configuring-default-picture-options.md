---
title: Configuration des options des images par défaut
TOCTitle: Configuration des options des images par défaut
ms:assetid: b1c986f0-6400-447a-9e36-78c1c3a4f793
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn205074(v=OCS.15)
ms:contentKeyID: 53901509
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des options des images par défaut

 

_**Dernière rubrique modifiée :** 2013-03-22_

Par défaut, les images des utilisateurs sont affichées automatiquement. Pour les masquer, les utilisateurs peuvent sélectionner l’option **Masquer mon image** dans le client Lync. Ce paramètre est toutefois ignoré par certaines autres applications Office.

Si la possibilité d’affichage des images même en cas de désactivation de cette option par l’utilisateur vous pose problème, vous pouvez modifier les paramètres d’affichage des images de Lync au niveau global, ou pour un site ou service spécifique, afin que les images des utilisateurs ne soient pas affichées par défaut. Utilisez l’applet de commande Lync Server Management Shell suivante pour que les images des utilisateurs ne soient pas affichées, sauf si ceux-ci sélectionnent l’option **Afficher mon image** de façon explicite dans le client :

    Set-CsPrivacyConfiguration -DisplayPublishedPhotoDefault $False

Pour plus d’informations sur cette applet de commande, voir [Set-CsPrivacyConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsPrivacyConfiguration) dans la documentation sur Lync Server Management Shell.

