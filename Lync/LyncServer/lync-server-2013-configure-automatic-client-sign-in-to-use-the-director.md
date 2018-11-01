---
title: "Lync Server 2013 : Conf. connexion auto. du client pour utiliser le directeur"
TOCTitle: Configuration de la connexion automatique du client pour utiliser le directeur
ms:assetid: 85369ffc-53ae-43be-8a23-84a094faecff
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398678(v=OCS.15)
ms:contentKeyID: 49297948
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration de la connexion automatique du client pour utiliser le directeur dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-08_

Quand vous déployez Lync Server 2013, un directeur ou un pool directeur, nous vous conseillons d’utiliser l’ouverture de session client automatique comme meilleure pratique. Pour plus d’informations sur la configuration des serveurs DNS pour l’ouverture de session client automatique, reportez-vous à [Enregistrements DNS requis pour la connexion automatique des clients dans Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md) dans la documentation de planification.

Si vous avez déjà déployé l’ouverture de session client automatique, consultez les sections suivantes pour la configurer sur votre ou vos directeurs.

## Instance de directeur unique

Si vous avez déjà déployé l’ouverture de session client automatique et qu’elle pointe vers un serveur frontal ou un pool de serveurs frontaux, vous devez modifier l’enregistrement DNS SRV de manière à pointer vers le directeur.

## Pool directeur

Si vous avez déjà déployé l’ouverture de session client automatique et qu’elle pointe vers un serveur frontal ou un pool de serveurs frontaux, vous devez modifier l’enregistrement DNS SRV de manière à pointer vers le pool directeur.

