---
title: "Lync Server 2013 : ut. du portail web d’admin. du syst. de salle Lync"
TOCTitle: Utilisation du portail web d’administration du système de salle Lync
ms:assetid: c387b2a3-3e42-4642-af72-88126ed2820f
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn743660(v=OCS.15)
ms:contentKeyID: 62268988
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Utilisation du portail web d’administration du système de salle Lync dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2014-11-10_

Une fois que vous avez déployé le stockage redondant en local (LRS) sur le serveur, vous pouvez vérifier le statut de toutes les salles LRS en vous connectant au portail web d’administration de LRS à partir d’un navigateur.

## Connexion

1.  Accédez à l’URL suivante :
    
    https://\<fe-server\>/lrs

2.  Entrez les données d’identification du compte LRSSupport ou d’un compte ajouté au groupe de sécurité LRSSupportAdminGroup.

![Écran Connexion au portail d’administration Lync Room System](images/Dn743660.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Écran Connexion au portail d’administration Lync Room System")

## Page Récapitulatif du portail web d’administration du stockage redondant en local

La page Récapitulatif fournit les informations ci-dessous pour toutes les salles de stockage redondant en local déployées sur le serveur :

  - **Libellé** : nom personnalisé que l’administrateur attribue à la salle. Le libellé peut être défini sur le portail en cliquant sur le nom de la salle.

  - **Intégrité** : statut d’intégrité de la salle, dérivé du statut d’intégrité agrégé de la salle, qui s’affiche sous la section Intégrité de la page Paramètres de la salle.

  - **Réunion suivante** : date et heure de la prochaine réunion prévue.

  - **Version, marque et modèle du stockage redondant en local** : ces valeurs sont prédéfinies dans le stockage redondant en local. Selon la marque, ces champs peuvent rester vides.

  - **Dernière actualisation** : affiche l’heure à laquelle la page web a été actualisée pour la dernière fois.

![Affichage de synthèse du portail d’administration Lync Room System](images/Dn743660.f829ce90-dd95-4725-bd94-6870c5dcf046(OCS.15).png "Affichage de synthèse du portail d’administration Lync Room System")

## Informations sur la salle de stockage redondant en local

La section Informations sur la salle du portail permet d’afficher et de configurer des salles de stockage redondant en local individuelles. Elle contient quatre sections : Paramètres, Détails, Journalisation et Intégrité.

## Paramètres

Dans la section Paramètres, vous pouvez définir le mot de passe, le libellé de la salle et les niveaux de volume par défaut pour la salle. Si vous configurez ces paramètres, les modifications sont répliquées uniquement après que vous avez redémarré la console de stockage redondant en local.

![Paramètre de la salle du portail d’administration Lync Room System](images/Dn743660.ab162e19-41ac-4991-9b2a-92575aa53eda(OCS.15).png "Paramètre de la salle du portail d’administration Lync Room System")

## Détails

La section Détails contient un récapitulatif en lecture seule des paramètres de la salle de stockage redondant en local, dont : heure de la dernière actualisation, réunion suivante, dernières opérations de mise à jour, de maintenance et d’étalonnage, paramètres par défaut de haut-parleur, de micro et de sonnerie, version, URI SIP, nombre d’écrans et détails de chaque écran, statut et activité.

![Affichage détaillé du portail d’administration Lync Room System](images/Dn743660.2958bbba-db74-4670-a920-87fdfb2fc22d(OCS.15).png "Affichage détaillé du portail d’administration Lync Room System")

## Journalisation

La section Journalisation peut être utilisée pour collecter à distance les journaux et les enregistrer à un emplacement spécifié. Vous pouvez également redémarrer la console de stockage redondant en local (interface utilisateur de stockage redondant en local) ou redémarrer tout le système.

![Connexion à la salle du portail d’administration Lync Room System](images/Dn743660.749aee71-deaa-4ace-a146-fe2b349f0f42(OCS.15).png "Connexion à la salle du portail d’administration Lync Room System")

## Intégrité

La section Intégrité fournit une indication visuelle de l’intégrité de la connexion à Lync Server, des périphériques audio, des périphériques vidéo, du statut de résilience et du dispositif d’affichage.

![Intégrité de la salle du portail d’administration Lync Room System](images/Dn743660.8cc644f8-8e3e-42d5-9079-045d8fe9daa7(OCS.15).png "Intégrité de la salle du portail d’administration Lync Room System")

## Remarques supplémentaires concernant le portail web d’administration

> [!NOTE]  
> <ul><li><p>Pour des raisons de sécurité, le portail web d’administration vous déconnecte automatiquement toutes les 15 minutes.</p></li><li><p>Les modifications des paramètres ne sont appliquées qu’une fois que le système de stockage redondant en local a été redémarré.</p></li><li><p>Sur le portail web d’administration du stockage redondant en local, les notifications sont mises en avant. En d’autres termes, elles ne disparaissent pas.</p></li>
> <li><p>Les notifications s’affichent uniquement une fois que vous avez actualisé la page.</p></li>
> <li><p>Le statut des salles de stockage redondant en local s’affiche une fois que vous avez actualisé la page.</p></li>
> <li><p>Si le mot de passe du compte LRSApp arrive à expiration, vous ne pourrez pas voir le statut des salles. Configurez le mot de passe du compte LRSAppuser de sorte qu’il n’arrive jamais à expiration ou veillez à le mettre à jour avant qu’il arrive à expiration.</p></li>
> <li><p>Le portail web d’administration du stockage redondant local est pris en charge pour les déploiements locaux uniquement.</p></li></ul>


## Identification et résolution des problèmes

## Pourquoi ne puis-je pas me connecter au portail web d’administration ?

  - Lorsque vous ouvrez https://localhost/lrs, vous découvrez la page de connexion, mais lorsque vous tapez vos données d’identification, vous ne parvenez pas à vous connecter. Dans ce cas, vous devez ouvrir https://FQDNofFEserver/lrs pour vous connecter au portail web d’administration.

  - Si l’ordinateur à partir duquel vous accédez au portail web d’administration appartient à un groupe de travail, « http:// » ne fonctionnera pas. Utilisez « https » à la place.

## Pourquoi ne puis-je pas voir le stockage redondant local sur le portail web d’administration ?

  - Assurez-vous que votre déploiement comporte des comptes de stockage redondant en local et qu’ils ont été créés selon les recommandations de déploiement du portail web d’administration du stockage redondant local. Assurez-vous que les comptes de stockage redondant en local sont mis en service avec Enable-CsMeetingRoom, et non Enable-CsUser, sur le serveur Lync.

  - Si vous avez créé des comptes de stockage redondant en local et que vous ne les voyez pas sur le portail web d’administration, collectez les journaux du serveur en utilisant l’outil de journalisation Lync Server avec le composant **MeetingPortal** sélectionné, puis envoyez-les à votre contact d’assistance pour le stockage redondant en local.

## Pourquoi ne puis-je pas voir le statut de stockage redondant en local sur le portail web d’administration ?

  - Assurez-vous que le compte d’utilisateur LRSApp est activé pour SIP.

  - Si vous rencontrez toujours des difficultés, extrayez le fichier **Trace.log** dans le système LRS sous D:\\Tracing\\LRSAdminLogs\\, puis envoyez-le à votre contact d’assistance pour le stockage redondant en local.

