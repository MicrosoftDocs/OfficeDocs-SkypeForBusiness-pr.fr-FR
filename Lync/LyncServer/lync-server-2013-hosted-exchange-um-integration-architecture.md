---
title: "Lync Server 2013 : Arch. d’intégr. de mess. unifiée Exchange hébergée"
TOCTitle: Architecture d’intégration de messagerie unifiée Exchange hébergée
ms:assetid: 0094d5dc-1836-441c-b6e2-f88e35203a8d
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398067(v=OCS.15)
ms:contentKeyID: 49296052
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Architecture d’intégration de messagerie unifiée Exchange hébergée dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-25_

L’application de routage ExUM Lync Server 2013 peut être intégrée à un déploiement de messagerie unifiée Exchange sur site, à un déploiement de messagerie unifiée Exchange hébergé par un fournisseur de service ou à une combinaison des deux. Le diagramme suivant montre les trois possibilités.

**Intégration à un déploiement de messagerie unifiée Exchange sur site et à deux déploiements Exchange hébergés par des fournisseurs de service**

![Déploiement UM Lync Server Exchange sur site](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "Déploiement UM Lync Server Exchange sur site")

Les modes suivants sont pris en charge :

  - **Déploiement sur site** : Lync Server 2013 et la messagerie unifiée Exchange sont déployés sur des serveurs locaux dans votre entreprise.

  - **Déploiement intersite** : Lync Server 2013 est déployé sur des serveurs locaux dans votre entreprise et la messagerie unifiée Exchange est hébergée par un fournisseur de service en ligne, par exemple, dans un centre de données Microsoft Exchange Online.

  - **Déploiement mixte** : votre déploiement de Lync Server 2013 comporte des boîtes aux lettres d’utilisateur hébergées sur des serveurs Exchange locaux dans votre entreprise et des boîtes aux lettres hébergées dans un centre de données de service Exchange hébergé.
    
    > [!NOTE]  
    > Le déploiement mixte peut tenir lieu de solution de transition au cours de l’évaluation et de la migration progressive des utilisateurs vers un service de messagerie unifiée Exchange hébergé, ou de solution permanente, si vous décidez de conserver sur site les services de messagerie unifiée Exchange de certains utilisateurs après en avoir transféré d’autres.

## Espace d’adressage SIP partagé

Pour intégrer Lync Server 2013 à un déploiement de messagerie unifiée Exchange sur site, vous devez autoriser Lync Server 2013 à lire des objets de services de domaine Active Directory de messagerie unifiée Exchange. Cependant, cette approche n’est pas adaptée pour l’intégration à un service de messagerie unifiée Exchange hébergé, car Lync Server 2013 et la messagerie unifiée Exchange sont installés dans des forêts distinctes sans aucune relation de confiance entre elles.

Pour intégrer Lync Server 2013 à un service de messagerie unifiée Exchange hébergé, vous devez configurer un *espace d’adressage SIP partagé* . Dans cette configuration, le même espace d’adressage de domaine SIP est disponible pour Lync Server 2013 et le fournisseur du service de messagerie unifiée Exchange hébergé.

> [!NOTE]  
> L’utilisation de l’espace d’adressage SIP partagé est similaire à l’approche utilisée dans un déploiement Lync Server 2013 intersite, dans lequel des utilisateurs sont hébergés dans le déploiement sur site tandis que d’autres sont hébergés dans un déploiement hébergé (tel qu’un déploiement de Lync Online). Le domaine SIP est fractionné entre les deux déploiements. Lorsque vous intégrez Lync Server 2013 à un service de messagerie unifiée Exchange hébergé, veillez à inclure le fournisseur du service de messagerie unifiée Exchange hébergé dans l’espace d’adressage SIP partagé.

Pour configurer l’espace d’adressage SIP partagé en vue de l’intégration de Lync Server à un service de messagerie unifiée Exchange hébergé, vous devez configurer le serveur Edge comme suit :

1.  Configurez le serveur Edge pour la fédération en exécutant l’applet de commande **Set-CsAccessEdgeConfiguration** qui permet de définir les paramètres suivants :
    
      - **UseDnsSrvRouting** indique que les serveurs Edge doivent reposer sur les enregistrements DNS SRV lors de l’envoi et la réception des demandes de fédération.
    
      - **AllowFederatedUsers** indique si des utilisateurs internes sont autorisés à communiquer avec des utilisateurs de domaines fédérés. Cette propriété détermine également si des utilisateurs internes peuvent communiquer avec des utilisateurs de domaines fractionnés.
    
      - **EnablePartnerDiscovery** indique si Lync Server 2013 utilisera des enregistrements DNS pour découvrir des domaines partenaires qui ne figurent pas dans la liste des domaines autorisés Active Directory. Si la valeur est False, Lync Server 2013 fédérera uniquement les domaines trouvés dans la liste des domaines autorisés. Ce paramètre est requis si vous utilisez le routage de service DNS. Dans la plupart des déploiements, la valeur est définie sur False pour empêcher l’ouverture de la fédération à tous les partenaires.

2.  Répliquez le magasin central de gestion sur le serveur Edge et vérifiez que la réplication s’est correctement effectuée. Pour plus d’informations, reportez-vous à [Exportation de la topologie Lync Server 2013 et copie vers le support externe de l’installation Edge](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) dans la documentation de déploiement.

3.  Configurez un *fournisseur d’hébergement* sur le serveur Edge en exécutant l’applet de commande **New-CsHostingProvider** qui permet de définir les paramètres suivants :
    
      - **Identity** spécifie un identificateur de valeur de chaîne unique pour le fournisseur d’hébergement que vous créez, par exemple, **Messagerie unifiée Exchange hébergée** .
    
      - **Enabled** indique si la connexion réseau entre votre domaine et le fournisseur d’hébergement est activée. La valeur doit être définie sur **True** .
    
      - **EnabledSharedAddressSpace** indique si le fournisseur d’hébergement sera utilisé dans un scénario d’espace d’adressage SIP partagé. La valeur doit être définie sur **True** .
    
      - **HostsOCSUsers** indique si le fournisseur d’hébergement est utilisé pour héberger les comptes Lync Server 2013. La valeur doit être définie sur **False** .
    
      - **ProxyFQDN** indique le nom de domaine complet du serveur proxy utilisé par le fournisseur d’hébergement, par exemple, **proxyserver.fabrikam.com** . Demandez cette information au fournisseur d’hébergement. Cette valeur ne peut pas être modifiée. Si le fournisseur d’hébergement change de serveur proxy, vous devrez supprimer et recréer l’entrée pour ce fournisseur.
    
      - **IsLocal** indique si le serveur proxy utilisé par le fournisseur d’hébergement est contenu dans votre topologie Lync Server 2013. La valeur doit être définie sur **False**.

