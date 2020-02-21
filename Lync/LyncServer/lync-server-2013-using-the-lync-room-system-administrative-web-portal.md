---
title: 'Lync Server 2013 : utilisation du portail Web d’administration de Lync Room System'
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
ms.openlocfilehash: d950bd62b2db91f60dd5828f79977472a9c5d573
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212670"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a>Utilisation du portail Web d’administration de Lync Room System dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-11-10_

Une fois que vous avez déployé LRS sur le serveur, vous pouvez vérifier l’état de toutes les salles de LRS en vous connectant au portail Web d’administration de LRS à partir d’un navigateur.

<div>

## <a name="sign-in"></a>Se connecter

1.  Accédez à l’URL suivante :
    
    https://\<serveur\>frontal/LRS

2.  Entrez les informations d’identification du compte LRSSupport ou d’un compte qui a été ajouté au groupe de sécurité LRSSupportAdminGroup.

![Écran de connexion du portail d’administration Lync Room System](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Écran de connexion du portail d’administration Lync Room System")

</div>

<div>

## <a name="lrs-administrative-web-portal-summary-page"></a>Page récapitulative du portail Web d’administration LRS

La page de résumé fournit les informations suivantes pour toutes les salles LRS déployées sur le serveur :

  - **Baliser**   le nom personnalisé que l’administrateur fournit à la salle. La balise peut être définie dans le portail en cliquant sur le nom de la salle.

  - **Intégrité**   l’état d’intégrité de la salle, qui est dérivé de l’état d’intégrité agrégé de la salle, qui s’affiche sous la section intégrité de la page Paramètres de la salle.

  - **Réunion suivante date**   et heure de la prochaine réunion planifiée.

  - **Version LRS, fabricant, modèle**   ces valeurs sont prédéfinies dans LRS. En fonction du fabricant, ces champs peuvent rester vides.

  - **Dernière actualisation**   : affiche la dernière fois que la page Web a été actualisée.

![Affichage de synthèse du portail d’administration de Lync Room System](images/Dn743660.f829ce90-dd95-4725-bd94-6870c5dcf046(OCS.15).png "Affichage de synthèse du portail d’administration de Lync Room System")

</div>

<div>

## <a name="lrs-room-information"></a>Informations sur la salle LRS

La section informations sur la salle du portail vous permet d’afficher et de configurer des salles LRS individuelles. Il contient quatre sections : paramètres, détails, résolution des problèmes et intégrité.

<div>

## <a name="settings"></a>Paramètres

Dans la section paramètres, vous pouvez définir le mot de passe, la balise Room et les niveaux de volume par défaut pour la salle. Si vous configurez ces paramètres, les modifications ne sont répliquées qu’une fois que vous avez redémarré la console LRS. Vous verrez uniquement les paramètres de mise à jour du système pour les systèmes de salle Lync qui sont la version 15,12 et les versions ultérieures.

![Paramètres de la salle du portail d’administration Lync Room System](images/Dn743660.ab162e19-41ac-4991-9b2a-92575aa53eda(OCS.15).png "Paramètres de la salle du portail d’administration Lync Room System")

</div>

<div>

## <a name="details"></a>Détails

La section Détails fournit une synthèse en lecture seule des paramètres de la salle LRS, notamment : l’heure de la dernière actualisation ; réunion suivante ; dernières mises à jour, maintenance et étalonnage ; paramètres de haut-parleur, micro et sonnerie par défaut ; version9.0.2 URI SIP ; nombre d’écrans et détails sur chaque écran ; État et activité.

![Affichage détaillé du portail d’administration de Lync Room System](images/Dn743660.2958bbba-db74-4670-a920-87fdfb2fc22d(OCS.15).png "Affichage détaillé du portail d’administration de Lync Room System")

</div>

<div>

## <a name="troubleshooting"></a>Résolution des problèmes

La section Troubleshooting peut être utilisée pour collecter des journaux à distance et les enregistrer à un emplacement spécifié. Vous pouvez également redémarrer la console LRS (interface utilisateur LRS) ou redémarrer l’ensemble du système. Pour collecter les journaux, fournissez un chemin d’accès au dossier au format spécifié et assurez-vous que le dossier dispose des autorisations d’écriture accordées au compte d’ordinateur LRS. Si la taille du journal est trop importante, la collecte des journaux peut prendre jusqu’à 5 minutes. L’actualisation de la page vous donnera le dernier État.

![Journalisation de la salle du portail d’administration de Lync Room System](images/Dn743660.749aee71-deaa-4ace-a146-fe2b349f0f42(OCS.15).png "Journalisation de la salle du portail d’administration de Lync Room System")

</div>

<div>

## <a name="health"></a>Intégrité

La section Health fournit une indication visuelle de l’intégrité de la connexion Lync Server, du périphérique audio, du périphérique vidéo, de l’état de résistance et de l’écran.

![Intégrité de la salle du portail d’administration Lync Room System](images/Dn743660.8cc644f8-8e3e-42d5-9079-045d8fe9daa7(OCS.15).png "Intégrité de la salle du portail d’administration Lync Room System")

</div>

</div>

<div>

## <a name="additional-notes-about-the-administrative-web-portal"></a>Remarques supplémentaires sur le portail Web d’administration

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>Les modifications de paramètres ne sont appliquées qu’après le redémarrage du système LRS.</P>
> <LI>
> <P>Si le mot de passe du compte LRSApp expire, vous ne pourrez pas voir l’état des salles. Configurez le mot de passe du compte LRSAppuser de sorte qu’il n’expire jamais, ou veillez à mettre à jour le mot de passe lorsqu’il est proche de son expiration.</P>
> <LI>
> <P>Le portail Web d’administration LRS est pris en charge uniquement pour les déploiements locaux.</P></LI></UL>



</div>

</div>

<div>

## <a name="frequently-asked-questions"></a>Forum Aux Questions

<div>

## <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a>Pourquoi ne puis-je pas me connecter au portail Web d’administration ?

  - Lorsque vous ouvrez https://localhost/lrs, vous pouvez voir la page de connexion, mais lorsque vous tapez vos informations d’identification, vous ne pouvez pas vous connecter. Dans ce cas, vous devez ouvrir https://FQDNofFEserver/lrs la session pour vous connecter au portail Web d’administration.

  - Si l’ordinateur à partir duquel vous accédez au portail Web d’administration se trouve dans un groupe de travail, « http:// » ne fonctionnera pas. Utilisez « HTTPS » à la place.

</div>

<div>

## <a name="why-cant-i-see-lrs-in-the-administrative-web-portal"></a>Pourquoi ne puis-je pas voir LRS dans le portail Web d’administration ?

  - Assurez-vous que vous disposez de comptes LRS dans votre déploiement et qu’ils sont créés conformément aux recommandations de déploiement du portail Web d’administration LRS. Assurez-vous que les comptes LRS sont mis en service à l’aide de Enable-CsMeetingRoom, et non pas Enable-CsUser, sur le serveur Lync.

  - Si vous avez créé des comptes LRS et que vous ne pouvez pas afficher les comptes dans le portail Web d’administration, collectez les journaux du serveur à l’aide de l’outil de journalisation Lync Server avec le composant **MeetingPortal** sélectionné, puis envoyez-les à votre contact de support LRS.

</div>

<div>

## <a name="why-cant-i-see-the-status-of-lrs-in-the-administrative-web-portal"></a>Pourquoi ne puis-je pas voir l’état de LRS dans le portail Web d’administration ?

  - Assurez-vous que le compte d’utilisateur LRSApp est compatible SIP.

  - Si vous rencontrez toujours des problèmes, récupérez le fichier **trace. log** dans le système LRS à partir\\de\\D\\: Tracing LRSAdminLogs, puis envoyez-le à votre contact de support LRS.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

