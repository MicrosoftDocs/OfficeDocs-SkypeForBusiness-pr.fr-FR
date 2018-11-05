---
title: "Lync Server 2013 : Conf. des numéros d’accès aux conférences rendez-vous"
TOCTitle: Configuration des numéros d’accès aux conférences rendez-vous
ms:assetid: d8a18030-f318-43dd-834d-70e5014b5e8a
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398952(v=OCS.15)
ms:contentKeyID: 49299014
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des numéros d’accès aux conférences rendez-vous dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2011-07-17_

Lorsque vous déployez des conférences rendez-vous, vous devez configurer les numéros de téléphone que les utilisateurs peuvent appeler à partir du réseau téléphonique commuté pour participer à la partie audio des conférences. Ces numéros s’affichent dans les invitations à une réunion et sur la page web des paramètres de configuration des conférences rendez-vous.

Avant de créer des numéros d’accès aux conférences rendez-vous, vous devez planifier vos régions de conférences rendez-vous puis configurer les plans de numérotation correspondants. Pour plus d’informations sur les régions, reportez-vous à [Configuration requise pour les conférences rendez-vous dans Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) dans la documentation de planification. Pour plus d’informations sur la configuration des plans de numérotation pour les conférences rendez-vous, reportez-vous à [Configuration des plans de numérotation pour les conférences rendez-vous dans Lync Server 2013](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md).

> [!NOTE]  
> Vous ne pouvez pas utiliser un nouveau numéro d’accès pour la conférence rendez-vous tant que la réplication AD DS de ce numéro n’est pas terminée. La réplication peut durer plusieurs heures.

> [!NOTE]  
> Une fois que vous avez créé les numéros d’accès aux conférences rendez-vous, vous pouvez modifier le nom complet des objets contact Active Directory pour permettre aux utilisateurs d’identifier plus facilement le numéro d’accès approprié. Utilisez l’applet de commande <strong>Set-CsDialInConferencingAccessNumber</strong> pour modifier le nom complet. Vous ne devez pas modifier manuellement les objets Active Directory. Pour plus d’informations sur la modification d’un numéro d’accès, reportez-vous à l’applet de commande <strong>Set-CsDialInConferencingAccessNumber</strong> dans la documentation Lync Server Management Shell.

## Dans cette section

[Création ou modification d’un numéro d’accès à une conférence rendez-vous dans Lync Server 2013](lync-server-2013-create-or-modify-a-dial-in-conferencing-access-number.md)

## Voir aussi

#### Concepts

[Configuration requise pour les conférences rendez-vous dans Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md)  

#### Autres ressources

[Configuration des plans de numérotation pour les conférences rendez-vous dans Lync Server 2013](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)

