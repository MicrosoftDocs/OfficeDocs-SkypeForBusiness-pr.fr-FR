---
title: "Configuration requise pour l’intégration de MLS 2013 et MES 2013"
TOCtitle: "Configuration requise pour l’intégration de MLS 2013 et MES 2013"
ms:assetid: ea22beb9-c02e-47cb-836d-97a556969052
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ721919(v=OCS.15)
ms:contentKeyID: 49891590
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration requise pour l’intégration de Microsoft Lync Server 2013 et Microsoft Exchange Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Avant de pouvoir intégrer Microsoft Lync Server 2013 et Microsoft Exchange Server 2013, vous devez vérifier que toutes les étapes préalables requises ont bien été effectuées. Évidemment, l’intégration ne peut pas avoir lieu tant que Exchange 2013 et Lync Server 2013 ne sont pas complètement installés et en état de fonctionner. Pour plus d’informations sur l’installation d’Exchange, voir la documentation concernant la planification et le déploiement d’Exchange 2013 à l’adresse [http://go.microsoft.com/fwlink/?linkid=268539\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=268539%26clcid=0x40c) (contenu éventuellement en anglais). Pour plus d’informations sur l’installation de Lync Server 2013, voir la documentation concernant la planification et le déploiement à l’adresse [http://go.microsoft.com/fwlink/?linkid=254806\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=254806%26clcid=0x40c) (contenu éventuellement en anglais).

Une fois les serveurs en état de fonctionnement, vous devez attribuer des certificats d’authentification de serveur à serveur à Lync Server 2013 et Exchange 2013. Ces certificats permettent à Lync Server et Exchange d’échanger des informations et de communiquer entre eux. Lorsque vous installez Exchange 2013, un certificat auto-signé ayant pour nom Certificat Auth Microsoft Exchange Server est créé pour vous. Ce certificat, que vous pouvez trouver dans le magasin de certificats de l’ordinateur local, doit être utilisé pour l’authentification de serveur à serveur sur Exchange 2013. Pour plus d’informations sur l’attribution de certificats dans Exchange 2013, voir la rubrique « Configure Mail Flow and Client Access » à l’adresse [http://go.microsoft.com/fwlink/?linkid=268540\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=268540%26clcid=0x40c) (contenu éventuellement en anglais).

Pour Lync Server 2013, vous pouvez utiliser un certificat Lync Server existant comme certificat d’authentification de serveur à serveur. Par exemple, votre certificat par défaut peut également être utilisé en tant que certificat OAuthTokenIssuer. Lync Server 2013 vous permet d’utiliser n’importe quel certificat de serveur web comme certificat pour l’authentification de serveur à serveur, à condition que :

  - le certificat inclue le nom de votre domaine SIP dans le champ Objet ;

  - le même certificat soit configuré comme certificat OAuthTokenIssuer sur tous vos serveurs frontaux ;

  - la longueur du certificat soit d’au moins 2 048 bits.

Pour plus d’informations sur les certificats d’authentification de serveur à serveur pour Microsoft Lync Server 2013, voir [Attribution d’un certificat d’authentification de serveur à serveur à Microsoft Lync Server 2013](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md) (contenu éventuellement en anglais).

Une fois les certificats attribués, vous devez configurer le service de découverte automatique sur Exchange 2013. Dans Exchange 2013, le service de découverte automatique configure des profils utilisateurs et fournit un accès aux services Exchange lorsque les utilisateurs se connectent au système. Les utilisateurs indiquent leur adresse de messagerie et leur mot de passe au service de découverte automatique ; le service fournit en retour à l’utilisateur des informations telles que :

  - les informations de connexion pour la connectivité interne et externe à Exchange 2013 ;

  - l’emplacement du serveur de boîte aux lettres de l’utilisateur ;

  - les URL pour les fonctionnalités Outlook telles que les informations sur la disponibilité, la messagerie unifiée et le carnet d’adresses en mode hors connexion ;

  - les paramètres de serveur d’Outlook Anywhere.

Le service de découverte automatique doit être configuré pour pouvoir intégrer Lync Server 2013 et Exchange 2013. Vous pouvez vérifier si le service a été configuré ou non en exécutant les commandes suivantes à partir d’Exchange Management Shell et en vérifiant la valeur de la propriété AutoDiscoverServiceInternalUri :

    Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List

Si cette valeur est vide, vous devez attribuer un URI au service de découverte automatique. Cet URI ressemble généralement à ceci :

    https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml

Vous pouvez attribuer l’URI de découverte automatique en exécutant une commande semblable à celle-ci :

    Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"

Pour plus d’informations sur le service de découverte automatique, voir la rubrique « Understanding the Autodiscover Service » à l’adresse [http://go.microsoft.com/fwlink/?linkid=268542\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=268542%26clcid=0x40c) (contenu éventuellement en anglais).

Une fois le service de découverte automatique configuré, vous devez modifier les paramètres de configuration OAuth de Lync Server. Vous vous assurez ainsi que Lync Server sait où trouver le service de découverte automatique. Pour modifier les paramètres de configuration OAuth dans Lync Server 2013, exécutez la commande suivante à partir de Lync Server Management Shell. Lors de l’exécution de la commande, assurez-vous de spécifier l’URI du service de découverte automatique exécuté sur votre serveur Exchange et d’utiliser **autodiscover.svc** pour pointer sur l’emplacement du service à la place de **autodiscover.xml** (qui pointe sur le fichier XML utilisé par ce service) :

    Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc

> [!NOTE]  
> La paramètre d’identité de la commande précédente est facultatif. En effet, Lync Server ne vous permet d’avoir qu’une seule collection globale de paramètres de configuration OAuth. Cela signifie, entre autres, que vous pouvez configurer l’URL de découverte automatique à l’aide d’une commande plus simple :<br />
Set-CsOAuthConfiguration–ExchangeAutodiscoverUrl &quot;https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc&quot;<br />
Si vous ne connaissez pas cette technologie, OAuth est un protocole d’autorisation standard utilisé par nombre des plus importants sites web. Grâce à OAuth, les informations d’identification et les mots de passe d’utilisateur ne sont pas transmis d’un ordinateur à un autre. L’authentification et l’autorisation sont basées sur l’échange de jetons de sécurité. Ces jetons octroient l’accès à un ensemble de ressources spécifique pour une durée spécifique.

En plus de configurer le service de découverte automatique, vous devez également créer un enregistrement DNS pour le service qui pointe sur votre serveur Exchange. Par exemple, si votre service de découverte automatique est situé à l’adresse autodiscover.litwareinc.com, vous devrez créer un enregistrement DNS pour autodiscover.litwareinc.com qui aboutit au nom de domaine complet de votre serveur Exchange (par exemple, atl-exchange-001.litwareinc.com).

