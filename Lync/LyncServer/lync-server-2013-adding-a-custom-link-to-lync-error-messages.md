---
title: 'Lync Server 2013 : ajout d’un lien personnalisé à des messages d’erreur Lync'
TOCTitle: Ajout d’un lien personnalisé à des messages d’erreur Lync
ms:assetid: de756088-fcc3-4e47-bde8-4fa4cc852fd1
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398979(v=OCS.15)
ms:contentKeyID: 53095543
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ajout d’un lien personnalisé à des messages d’erreur Lync dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-20_

Personnalisez les messages d’erreur Lync 2013 en ajoutant un lien vers vos informations d’identification et de résolution des problèmes ou d’assistance technique. À cet effet, utilisez l’applet de commande **New-CSClientPolicy** ou **Set-CSClientPolicy** Lync Server Management Shell avec le paramètre CustomLinkInErrorMessages. Le texte du lien personnalisé est « Cliquez ici pour consulter les rubriques d’aide mises à disposition par votre administrateur » et il ne peut pas être personnalisé.

Par exemple, la commande ci-dessous entraîne l’affichage du lien personnalisé dans la zone de pied de page de chaque message d’erreur Lync 2013 et définit la cible du lien sur http://contoso.com/help/LyncHelpDesk.aspx:

    New-CsClientPolicy -Identity LyncErrorLink -CustomLinkInErrorMessages "http://contoso/help/LyncHelpDesk.aspx"

Utilisez **Grant-CSClientPolicy** pour affecter cette nouvelle stratégie à des utilisateurs. Pour plus d’informations, reportez-vous à **New-CSClientPolicy** et à **Grant-CSClientPolicy** dans la documentation de Lync Server Management Shell.

