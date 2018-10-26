---
title: "Lync Server 2013 : Vérif. de la connectivité pour les utilisateurs externes"
TOCTitle: Vérification de la connectivité pour les utilisateurs externes
ms:assetid: 5c02bd6e-1c96-448a-a21d-58c9961c6640
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398402(v=OCS.15)
ms:contentKeyID: 49297314
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vérification de la connectivité pour les utilisateurs externes dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-19_

La validation de la connectivité pour les utilisateurs externes nécessite de s’assurer de la connectivité des utilisateurs vers le serveur et le port pour le service Edge d’accès.

Le site de l’Analyseur de connectivité à distance (<https://www.testocsconnectivity.com/>) est une ressource très utile pour vérifier votre configuration, la connexion, ainsi que l’envoi et la réception des messages appropriés pour les scénarios nécessaires à l’accès des utilisateurs externes. Le site est géré par le service de support technique Microsoft. Pour accéder à l’Analyseur de connectivité à distance, ouvrez le site web dans un navigateur et suivez les instructions relatives à la sélection du scénario.

## Tester la connectivité des utilisateurs externes et de l’accès externe

Les tests d’accès des utilisateurs externes doivent inclure tous les types d’utilisateurs externes pris en charge par votre organisation, dont un ou plusieurs des éléments suivants :

  - Utilisateurs d’au moins un domaine fédéré et test de la messagerie instantanée, de la présence et du partage du Bureau.

  - Utilisateurs de chaque fournisseur de services de messagerie instantanée public pris en charge par votre organisation (et pour lequel le provisionnement a été effectué).

  - Utilisateurs anonymes.

  - Utilisateurs appartenant à votre organisation, qui sont connectés à Lync à distance, mais n’utilisent pas VPN.

Ces tests déterminent si votre serveur Edge :

  - Écoute sur les ports requis à l’aide d’un client telnet depuis l’extérieur de votre réseau.
    
      - Exemple : telnet sip.contoso.com 443
    
      - Effectuez le test précédent sur les ports que vous utilisez sur le serveur Edge ou le pool de serveur Edge en fonction de votre déploiement.

  - Effectuer une résolution DNS externe précise.
    
      - Depuis l’extérieur de votre réseau, exécutez la commande ping sur chacun des noms de domaine complets (FQDN) externes de votre serveur Edge ou pool de serveurs Edge. Même si la commande ping échoue, vous obtiendrez les adresses IP que vous pouvez comparer à celles que vous avez affectées.

