---
title: Liste de vérification du déploiement de la jonction SIP
TOCTitle: Liste de vérification du déploiement de la jonction SIP
ms:assetid: 94f4f03e-19d5-4198-92be-e4076dbb959a
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398755(v=OCS.15)
ms:contentKeyID: 49298110
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Liste de vérification du déploiement de la jonction SIP pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-21_

Avant de pouvoir déployer une jonction SIP, vous devez échanger avec votre fournisseur de services certaines informations de connexion de base concernant vos points de terminaison de jonction SIP respectifs.

Récupérez les informations suivantes pour chaque passerelle du fournisseur de services de téléphonie Internet (ITSP) à laquelle vous vous connecterez :

  - Adresse IP

  - Nom de domaine complet (FQDN)

> [!NOTE]  
> Le fournisseur de services peut vous demander de vous connecter à plusieurs passerelles ITSP. Dans ce cas, vous devez configurer une connexion entre chaque passerelle ITSP et chaque serveur de médiation dans votre pool.

Les informations que vous donnez à votre fournisseur de services dépendent du type de connexion de votre jonction SIP :

  - Pour les connexions réseau MPLS ou privées, donnez au fournisseur de services de téléphonie Internet l’adresse IP publiquement routable du routeur dans votre réseau de périmètre (appelé également zone démilitarisée, zone DMZ et sous-réseau filtré). Vérifiez que la passerelle ou le contrôleur SBC chez le fournisseur de services de téléphonie Internet peut atteindre cette adresse. Donnez également au fournisseur ITSP le nom de domaine complet de votre serveur de médiation.

  - Pour les connexions VPN, donnez au fournisseur ITSP l’adresse IP de votre serveur VPN.

## Considérations relatives aux certificats

Pour déterminer si vous avez besoin d’un certificat pour la jonction SIP, vérifiez avec votre fournisseur ITSP la prise en charge de protocole :

1.  Si votre fournisseur ITSP prend uniquement en charge TCP, vous n’avez pas besoin de certificat.

2.  Si votre fournisseur ITSP prend en charge TLS, il doit vous fournir un certificat.

> [!NOTE]  
> Le protocole SIP fonctionne conjointement avec les protocoles RTP ou SRTP, qui gèrent les données vocales réelles dans les appels VoIP.

## Processus de déploiement

Pour implémenter le côté Lync Server de la connexion de jonction SIP, procédez comme suit :

1.  À l’aide du Générateur de topologieLync Server, créez et configurez la topologie de domaine SIP. Pour plus d’informations, reportez-vous à [Définition et configuration d’une topologie dans le générateur de topologie pour Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md) dans la documentation de déploiement.

2.  À l’aide du Panneau de configuration Lync Server, configurez le routage des communications vocales pour le nouveau domaine SIP. Pour plus d’informations, reportez-vous à [Configuration des jonctions dans Lync Server 2013](lync-server-2013-configuring-trunks.md) dans la documentation de déploiement.

3.  Testez la connectivité à l’aide de l’applet de commande **Test-CsPstnOutboundCall**. Pour plus d’informations, reportez-vous à la documentation de Lync Server Management Shellou l’Aide de Lync Server Management Shell.

