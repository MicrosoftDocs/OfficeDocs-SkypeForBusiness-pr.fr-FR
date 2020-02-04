---
title: 'Lync Server 2013 : utilisation du portail web d’administration du système de salle Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Lync Room System Administrative Web Portal
ms:assetid: c387b2a3-3e42-4642-af72-88126ed2820f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743660(v=OCS.15)
ms:contentKeyID: 62268951
ms.date: 11/13/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c891309d76dda20f875592841925c852fe2e3351
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743934"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a>Utilisation du portail web d’administration du système de salle Lync dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-11-10_

Après le déploiement de LRS sur le serveur, vous pouvez vérifier l’état de toutes les pièces LRS en vous connectant au portail Web d’administration LRS à partir d’un navigateur.

<div>

## <a name="sign-in"></a>Connexion

1.  Accédez à l’URL suivante :
    
    https://\<Fe-Server\>/LRS

2.  Entrez les informations d’identification pour le compte LRSSupport ou un compte qui a été ajouté au groupe de sécurité LRSSupportAdminGroup.

![Écran Connexion au portail d’administration Lync Room System](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Écran Connexion au portail d’administration Lync Room System")

</div>

<div>

## <a name="lrs-administrative-web-portal-summary-page"></a>Page de résumé du portail Web d’administration LRS

La page résumé fournit les informations suivantes pour toutes les salles de LRS déployées sur le serveur :

  - **Marquez**   le nom personnalisé que l’administrateur accorde à la salle. Le libellé peut être défini sur le portail en cliquant sur le nom de la salle.

  - **État d'** intégrité de la salle, qui est dérivée de l’état d’intégrité agrégé de la salle, qui s’affiche dans la section intégrité de la page Paramètres de la salle.   

  - **Prochaine réunion**   , la date et l’heure auxquelles la prochaine réunion est planifiée.

  - **LRS version, fabricant, modèle**   ces valeurs sont prédéfinies dans LRS. Selon la marque, ces champs peuvent rester vides.

  - **Le dernier rafraîchissement**   affiche la dernière fois que la page Web a été actualisée.

![Affichage de synthèse du portail d’administration Lync Room System](images/Dn743660.f829ce90-dd95-4725-bd94-6870c5dcf046(OCS.15).png "Affichage de synthèse du portail d’administration Lync Room System")

</div>

<div>

## <a name="lrs-room-information"></a>Informations sur la salle LRS

La section infos sur la salle du portail vous permet d’afficher et de configurer des salles LRS individuelles. Il contient quatre sections : paramètres, détails, résolution des problèmes et santé.

<div>

## <a name="settings"></a>Paramètres

Dans la section Paramètres, vous pouvez définir le mot de passe, le libellé de la salle et les niveaux de volume par défaut pour la salle. Si vous configurez ces paramètres, les modifications sont répliquées uniquement après le redémarrage de la console LRS. Vous ne verrez que les paramètres système pour les systèmes de salle Lync version 15,12 et les versions ultérieures.

![Paramètre de la salle du portail d’administration Lync Room System](images/Dn743660.ab162e19-41ac-4991-9b2a-92575aa53eda(OCS.15).png "Paramètre de la salle du portail d’administration Lync Room System")

</div>

<div>

## <a name="details"></a>Détails

La section Détails fournit une synthèse en lecture seule des paramètres de la salle de LRS, notamment : l’heure de la dernière actualisation ; réunion suivante ; dernières mises à jour, maintenance et calibrage ; paramètres de haut-parleur, micro et sonnerie par défaut ; version9.0.2 URI SIP ; nombre d’écrans et de détails relatifs à chaque écran ; État et activité.

![Affichage détaillé du portail d’administration Lync Room System](images/Dn743660.2958bbba-db74-4670-a920-87fdfb2fc22d(OCS.15).png "Affichage détaillé du portail d’administration Lync Room System")

</div>

<div>

## <a name="troubleshooting"></a>Résolution des problèmes

La section Dépannage peut être utilisée pour collecter à distance les journaux et les enregistrer à un emplacement spécifié. Vous pouvez également redémarrer la console LRS (interface utilisateur d’LRS) ou redémarrer tout le système. Pour recueillir les journaux, spécifiez un chemin d’accès au dossier au format spécifié et assurez-vous que le dossier possède des autorisations d’écriture fournies au compte d’ordinateur LRS. Si la taille du journal est trop volumineuse, la collecte peut prendre jusqu’à 5 minutes. Actualisez la page pour obtenir le dernier statut.

![Connexion à la salle du portail d’administration Lync Room System](images/Dn743660.749aee71-deaa-4ace-a146-fe2b349f0f42(OCS.15).png "Connexion à la salle du portail d’administration Lync Room System")

</div>

<div>

## <a name="health"></a>Intégrité

La section santé donne une indication visuelle de l’état de la connexion du serveur Lync, du périphérique audio, du périphérique vidéo, de l’état de résilience et du périphérique d’écran.

![Intégrité de la salle du portail d’administration Lync Room System](images/Dn743660.8cc644f8-8e3e-42d5-9079-045d8fe9daa7(OCS.15).png "Intégrité de la salle du portail d’administration Lync Room System")

</div>

</div>

<div>

## <a name="additional-notes-about-the-administrative-web-portal"></a>Remarques supplémentaires concernant le portail Web d’administration

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>Les modifications apportées aux paramètres ne s’appliquent qu’après le redémarrage du système LRS.</P>
> <LI>
> <P>Si le mot de passe du compte LRSApp arrive à expiration, vous ne pourrez pas voir le statut des salles. Configurez le mot de passe du compte LRSAppuser pour qu’il n’expire jamais, ou veillez à mettre à jour le mot de passe en cas d’expiration proche.</P>
> <LI>
> <P>Le portail Web d’administration LRS est uniquement pris en charge pour les déploiements sur site.</P></LI></UL>



</div>

</div>

<div>

## <a name="frequently-asked-questions"></a>Forum aux questions

<div>

## <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a>Pourquoi ne puis-je pas me connecter au portail Web d’administration ?

  - Lorsque vous ouvrez https://localhost/lrsla page de connexion, vous pouvez voir la page de connexion, mais si vous entrez vos informations d’identification, vous ne pourrez pas vous connecter. Dans ce cas, vous devez ouvrir https://FQDNofFEserver/lrs pour vous connecter au portail Web d’administration.

  - Si l’ordinateur à partir duquel vous accédez au portail Web d’administration se trouve dans un groupe de travail, « http:// » ne fonctionnera pas. Utilisez plutôt « HTTPS ».

</div>

<div>

## <a name="why-cant-i-see-lrs-in-the-administrative-web-portal"></a>Pourquoi ne puis-je pas voir LRS dans le portail Web d’administration ?

  - Vérifiez que vous disposez de comptes LRS dans votre déploiement et qu’ils sont créés conformément aux recommandations en matière de déploiement de portail Web LRS d’administration. Assurez-vous que les comptes LRS sont approvisionnés à l’aide de Enable-CsMeetingRoom, et non d’Enable-CsUser, sur le serveur Lync.

  - Si vous avez créé des comptes LRS et ne pouvez pas voir les comptes dans le portail Web administratif, recueillez les journaux du serveur à l’aide de l’outil de journalisation de Lync Server avec le composant **MeetingPortal** sélectionné, puis envoyez-les à votre contact du support technique LRS.

</div>

<div>

## <a name="why-cant-i-see-the-status-of-lrs-in-the-administrative-web-portal"></a>Pourquoi ne puis-je pas voir l’état de LRS dans le portail Web d’administration ?

  - Assurez-vous que le compte d’utilisateur LRSApp est activé pour SIP.

  - Si vous rencontrez encore des problèmes, collectez le fichier **trace. log** dans le système LRS à partir\\de\\D\\: Tracing LRSAdminLogs, puis envoyez-le à votre contact du support technique LRS.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

