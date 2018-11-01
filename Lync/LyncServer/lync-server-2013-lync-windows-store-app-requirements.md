---
title: Configuration requise de l’application Lync du Windows Store
TOCTitle: Configuration requise de l’application Lync du Windows Store
ms:assetid: 5f2e0a40-8450-4f61-b6f6-913fc1906020
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ823129(v=OCS.15)
ms:contentKeyID: 53095433
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration requise de l’application Lync du Windows Store

 

_**Dernière rubrique modifiée :** 2016-12-08_

Les organisations dotées d’un déploiement local de Lync Server doivent satisfaire les exigences suivantes pour prendre en charge application Lync du Windows Store :

> [!NOTE]  
> Pour Lync Server 2010, exécuter la mise à jour cumulative pour Lync Server 2010 de février 2012 (disponible à l’adresse <a href="http://go.microsoft.com/fwlink/?linkid=3052%26kbid=2670352" class="uri">http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2670352</a>) ou une version supérieure sur tous les serveurs. Pour permettre aux utilisateurs de participer à des réunions, exécuter la mise à jour cumulative pour Lync Server 2010 d’octobre 2012 (disponible à l’adresse <a href="http://go.microsoft.com/fwlink/?linkid=3052%26kbid=2737915" class="uri">http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2737915</a>) sur les serveurs.

  - Activer les services de découverte automatique, Lync Web App et de ticket web sur le serveur.

  - Activer l’authentification par certificat sur le serveur frontal ou le pool de serveurs frontaux. (Le processus d’enregistrement des utilisateurs sur le serveur frontal ou le pool de serveurs frontaux est souvent appelé serveur d’inscriptions avancé.) Pour plus d’informations, voir [Créer des paramètres de configuration d’un serveur d’inscriptions](lync-server-2013-create-registrar-configuration-settings.md).

  - Publier les enregistrements des ressources (CNAME) d’alias DNS pour le service de découverte automatique.

  - Il n’est plus impératif de vérifier que le point de distribution de liste de révocation de certificats pour les certificats émis sur le serveur Lync pointe vers une ressource HTTP plutôt qu’une ressource LDAP. Vous devez toutefois vérifier que les dernières mises à jour de Windows sont installées sur les ordinateurs clients.

  - Configurer les proxys HTTP dans l’entreprise pour autoriser le trafic HTTP lié au serveur Lync. Ajouter des exceptions pour les services de découverte automatique, Lync Web App et de ticket web, au besoin.

  - Sur les clients, installez Windows 8.1 et la version la plus récente de application Lync du Windows Store pour résoudre un problème de connexion qui se produit généralement lorsque plusieurs domaines sont utilisés (par exemple, lorsque l’URI SIP est **userA@domainZ.com** mais que le serveur Edge est **sip.domainX.com**).

Si votre organisation s’abonne à Lync Online ou Office 365 et que vous utilisez votre propre nom de domaine, vous devez effectuer d’autres étapes pour configurer votre réseau pour la découverte automatique des serveurs Lync. La configuration requise pour le réseau est la même pour l’application Lync du Windows Store et Lync sur les appareils mobiles. Suivez les instructions de configuration du réseau dans l’article « Configurer les appareils mobiles Lync » du Wiki sur Office 365, accessible à l’adresse [http://go.microsoft.com/fwlink/?LinkId=271822](http://go.microsoft.com/fwlink/?linkid=271822).

## Voir aussi

#### Concepts

[Déploiement de l’application Lync du Windows Store](lync-server-2013-deploying-lync-windows-store-app.md)

