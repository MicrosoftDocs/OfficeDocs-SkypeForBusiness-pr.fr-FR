---
title: 'Lync Server 2013 : Scénarios de proxy inverse'
TOCTitle: Scénarios de proxy inverse
ms:assetid: 13108f59-a660-4ff1-8404-079d1cb646f2
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204691(v=OCS.15)
ms:contentKeyID: 49296316
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Scénarios de proxy inverse dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-01-21_

Les proxys inverses sont nécessaires dans Lync Server 2013 pour fournir l’accès aux services et ressources, tels que les URL simples de rendez-vous et de réunion, les carnets d’adresses, le contenu des réunions, le développement de listes de distribution et les services de mobilité. Le scénario de proxy inverse typique dans Lync Server 2013 consiste à accorder aux clients externes (par exemple, le client de bureau ou le client Lync Web App ) l’accès aux services web externes de directeur ou de serveur frontal.

**Proxy inverse et services web externes**

![Proxy inverse et services web externes](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "Proxy inverse et services web externes")

Lors de la phase de planification, vous définissez les exigences du proxy inverse dans un déploiement de Lync Server 2013. Le proxy inverse permet aux clients externes suivants d’accéder à des fonctionnalités :

  - Microsoft Lync 2013nm-client-w15-formal

  - Microsoft Lync Web App

  - Microsoft Lync Mobile

  - application Lync du Windows Store

Quand vous planifiez le déploiement de Lync Server 2013, vous mappez les exigences réelles de Lync Server 2013 sur les fonctionnalités du proxy inverse.

1.  Les clients externes se connecteront au proxy inverse sur le port TCP 443 et utiliseront le protocole SSL ou TLS. Les clients Microsoft Lync Mobile peuvent se connecter sur le port TCP 80, mais uniquement lors de la connexion initiale aux services de découverte de Lync et quand l’administrateur a configuré les enregistrements (ou alias) CNAME DNS adéquats et qu’il accepte que cette communication ne soit pas chiffrée.

2.  Les services web externes Lync Server 2013 (déployés sur le serveur frontal et/ou sur le directeur) attendent une connexion SSL/TLS depuis un proxy inverse sur le port TCP 4443.
    
    > [!IMPORTANT]  
    > Les ports d’écoute par défaut suggérés pour les services web externes sont le port TCP 8080 pour le trafic HTTP et le port TCP 4443 pour le trafic HTTPS. Le Générateur de topologie vous permet de remplacer les valeurs par défaut par vos propres ports d’écoute pour les services web externes. Il est important de noter que le proxy inverse communique avec les services web externes et que les clients externes communiquent avec le proxy inverse. Le client externe communique avec le proxy inverse sur le port TCP 443, mais vous pouvez redéfinir le port sur lequel le proxy inverse communique avec les services web externes. Les options du Générateur de topologie qui permettent de redéfinir les ports d’écoute par défaut pour les services web peuvent s’avérer utiles pour résoudre les conflits de port d’écoute susceptibles de se produire dans votre infrastructure.

3.  Les services web externes Lync Server 2013 attendent un en-tête d’hôte non modifié du client pour identifier le service et le répertoire du serveur web que le client essaie d’utiliser. Les demandes doivent s’afficher comme si elles provenaient du proxy inverse.

4.  Les services web externes utilisent des répertoires virtuels de serveur web définis qui fournissent les services proposés aux clients. Les services web spécifiques identifiables de manière externe sont :
    
      - Le répertoire virtuel « Meet  » pour les réunions de conférence web.
    
      - Le répertoire virtuel « Dialin » pour l’accès au téléphone et la téléconférence.
    
      - Le répertoire virtuel « Autodiscover » pour l’application Lync du Windows Store, Lync Mobile et le client de bureau Lync 2013. La découverte automatique dans Lync Server 2013 est connue sous le nom DNS « lyncdiscover ».
    
      - Les services non définis sont accessibles par le client externe via des appels directs aux services web externes. Par exemple, l’expansion du groupe de distribution et le service de carnet d’adresses sont accessibles via des appels directs aux services web externes et aux répertoires virtuels associés. Le client connaît le chemin d’accès réel du répertoire virtuel et construit une URL basée sur cette information. Le client peut accéder au service de carnet d’adresses à l’aide d’une URL telle que `https://externalweb.contoso.com/abs/handler`.
    
      - Lors de l’utilisation de la fonctionnalité de conférence, Office Web Apps Server est défini et configuré dans le cadre de la topologie Lync Server.
        
        > [!NOTE]  
        > Office Web Apps Server est un serveur de rôles distinct et n’est pas configuré dans le cadre des services web externes. Ce serveur est publié séparément pour l’accès client.

5.  Définissez un pontage SSL pour chaque service. Le port externe TCP 443 est mappé sur le port de services web externes TCP 4443. Pour le trafic HTTP non chiffré, le port TCP 80 est mappé sur le port de services web externes TCP 8080.

6.  Planifier les écouteurs du proxy inverse pour publier les ressources du serveur web

7.  Demandez et configurez le certificat pour le proxy inverse en fonction des services à proposer. S’il est configuré avec les autres noms du sujet adéquats, ce certificat peut être partagé par tous les écouteurs configurés sur le server proxy inverse.

Ressources disponibles pour planifier le déploiement de votre proxy inverse :

  - [Collecte des données dans Lync Server 2013](lync-server-2013-data-collection.md)

  - [Résumé des certificats - Proxy inverse dans Lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [Résumé des ports - Proxy inverse dans Lync Server 2013](lync-server-2013-port-summary-reverse-proxy.md)

  - [Résumé DNS - Proxy inverse dans Lync Server 2013](lync-server-2013-dns-summary-reverse-proxy.md)

