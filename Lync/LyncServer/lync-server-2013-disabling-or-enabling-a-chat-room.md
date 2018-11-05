---
title: 'Lync Server 2013 : Désactivation ou activation d’une salle de conversation'
TOCTitle: Désactivation ou activation d’une salle de conversation
ms:assetid: db0908fc-aae3-46e8-bc0b-245e9adfa1e2
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ215883(v=OCS.15)
ms:contentKeyID: 49299030
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Désactivation ou activation d’une salle de conversation dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2014-02-05_

Si le sujet d’une salle de conversation permanente n’est plus pertinent, vous pouvez rendre la salle de conversation inaccessible aux utilisateurs en la désactivant. Lorsqu’une salle de conversation est désactivée, tous les membres sont immédiatement déconnectés de la salle. Une fois une salle de conversation désactivée, les utilisateurs ne peuvent ni la rejoindre, ni la trouver lors de recherches de salles de conversation.

Une salle de conversation désactivée peut être activée ultérieurement par un administrateur de conversation permanente. Si une salle de conversation est désactivée, sa liste d’adhésion et d’autres paramètres sont conservés. Si vous la réactivez, vous n’avez pas besoin de recréer manuellement les paramètres.

Si l’historique de la salle de conversation est conservé (la conservation de l’historique d’une salle de conversation est un paramètre facultatif lié à une catégorie qui s’applique à toutes les salles au sein de la catégorie ; par défaut, il est conservé, mais l’option peut être désactivée en définissant le paramètre **Activer l’historique des conversations** de la catégorie sur false), le contenu est conservé si la salle est désactivée. Cependant, le contenu ne s’affichera pas dans les recherches tant que la salle de conversation demeurera dans son état de désactivation. Si vous activez ensuite la salle de conversation, les utilisateurs peuvent alors rechercher des messages ayant été publiés avant la désactivation de la salle.

Pour plus d’informations sur la désactivation et l’activation des salles de conversation à l’aide de l’interface de ligne de commande Windows PowerShell, reportez-vous à « Gestion des salles » dans [Configuration du serveur de conversation permanentte avec les applets de commande Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md). Pour désactiver une salle de conversation, utilisez une commande de type :

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $True

Pour activer une salle de conversation, définissez la propriété Disabled sur False :

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $False

Notez que vous ne pouvez pas utiliser Panneau de configuration Lync Server pour activer ou désactiver des salles de conversation.

Pour plus d’informations sur la configuration des salles de configuration, reportez-vous à [Configuration des salles dans in Lync Server 2013](lync-server-2013-configure-rooms.md) dans la documentation de déploiement.

