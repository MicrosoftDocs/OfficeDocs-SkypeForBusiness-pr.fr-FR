---
title: 'Lync Server 2013 : ajout de texte personnalisé dans des messages instantanés'
TOCTitle: Ajout de texte personnalisé dans des messages instantanés
ms:assetid: cabcc3ec-9d35-42ac-a403-e21b7d538c2c
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398847(v=OCS.15)
ms:contentKeyID: 53095530
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ajout de texte personnalisé dans des messages instantanés dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-20_

Ajoutez une exclusion ou un avertissement au début de chaque conversation de messagerie instantanée (IM) Lync 2013 en utilisant l’applet de commande **New-CSClientPolicy** ou **Set-CSClientPolicy**Lync Server Management Shell avec le paramètre IMWarning.

La commande présentée dans l’exemple ci-dessous ajoute un rappel de sécurité dans la partie supérieure de la fenêtre de conversation chaque fois qu’une nouvelle conversation de messagerie instantanée commence :

    New-CsClientPolicy -Identity IMSecurityNotice -IMWarning 
    "Remember, security is everyone's responsibility. Keep it confidential."

Utilisez **Grant-CSClientPolicy** pour affecter cette nouvelle stratégie à des utilisateurs. Pour plus d’informations, reportez-vous à **New-CSClientPolicy** et à **Grant-CSClientPolicy** dans la documentation de Lync Server Management Shell.

