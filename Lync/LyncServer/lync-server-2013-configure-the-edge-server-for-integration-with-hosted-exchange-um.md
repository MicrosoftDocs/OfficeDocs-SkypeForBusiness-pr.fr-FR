---
title: "Lync Server 2013 : Conf. serv. Edge pour l’int. à la mes. Unif. Exchange héb."
TOCTitle: Configuration du serveur Edge pour l’intégration à la messagerie unifiée Exchange hébergée
ms:assetid: ede3f2f9-f412-418e-a705-8d8ec98176c5
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg399075(v=OCS.15)
ms:contentKeyID: 49299281
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration du serveur Edge pour l’intégration à la messagerie unifiée Exchange hébergée

 

_**Dernière rubrique modifiée :** 2015-01-23_

Pour fournir à vos utilisateurs Lync Server 2013 des fonctionnalités de messagerie vocale sur une messagerie unifiée Exchange hébergée, vous devez effectuer les tâches de configuration suivantes sur le serveur Edge :

  - Configurez le serveur Edge pour la fédération.

  - Répliquez le magasin central de gestion sur le serveur de périphérie et vérifiez que la réplication s’est correctement effectuée.

  - Créez un fournisseur d’hébergement sur le serveur de périphérie.

Pour plus d’informations, reportez-vous à la documentation de Lync Server Management Shell pour les applets de commande suivantes :

  - [Set-CsAccessEdgeConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsAccessEdgeConfiguration)

  - [New-CsHostingProvider](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsHostingProvider)

> [!IMPORTANT]  
> Avant d’effectuer ces étapes, vous devez créer un enregistrement SRV DNS pour le service Exchange d’hébergement. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md">Création d’un enregistrement SRV DNS pour l’intégrer à la messagerie unifiée Exchange hébergée</a>.

## Pour configurer le serveur de périphérique pour la fédération

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Exécutez l’applet de commande Set-CsAccessEdgeConfiguration pour configurer le serveur pour la fédération. Par exemple, exécutez :
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -AllowFederatedUsers 1 -EnablePartnerDiscovery 0
    
    L’exemple qui précède définit les paramètres suivants :
    
      - **UseDnsSrvRouting** indique que les serveurs Edge doivent reposer sur les enregistrements DNS SRV lors de l’envoi et la réception des demandes de fédération.
    
      - **AllowFederatedUsers** indique si des utilisateurs internes sont autorisés à communiquer avec des utilisateurs de domaines fédérés. Cette propriété détermine également si des utilisateurs internes peuvent communiquer avec des utilisateurs de domaines fractionnés.
    
      - **EnablePartnerDiscovery** indique si Lync Server utilisera des enregistrements DNS pour essayer de découvrir des domaines partenaires qui ne figurent pas dans la liste des domaines autorisés Active Directory. Si la valeur est False, Lync Server 2013 n’est fédéré qu’avec les domaines trouvés dans la liste des domaines autorisés. Ce paramètre est requis si vous utilisez le routage de service DNS. Dans la plupart des déploiements, la valeur est définie sur False pour empêcher l’ouverture de la fédération à tous les partenaires.

## Pour répliquer des données sur le serveur de périphérie et vérifier que la réplication s’est correctement effectuée

  - Vérifiez que la réplication du serveur de périphérie est complète. Pour connaître la procédure, reportez-vous à [Vérification de la connectivité entre les serveurs internes et les serveurs Edge dans Lync Server 2013](lync-server-2013-verify-connectivity-between-internal-servers-and-edge-servers.md) (contenu éventuellement en anglais).

## Pour créer un fournisseur d’hébergement sur le serveur de périphérie

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Exécutez l’applet de commande **New-CsHostingProvider** pour configurer le fournisseur d’hébergement. Par exemple, exécutez :
    
        New-CsHostingProvider -Identity Fabrikam.com -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFQDN "proxyserver.fabrikam.com" -IsLocal $False -VerificationLevel UseSourceVerification
    
    L’exemple qui précède définit les paramètres suivants :
    
      - **Identity** spécifie un identificateur de valeur de chaîne unique pour le fournisseur d’hébergement que vous créez, par exemple, **Fabrikam.com** . Notez que la commande échouera si un fournisseur existant a déjà été configuré avec ce paramètre Identity.
    
      - **Enabled** indique si la connexion réseau entre votre domaine et le fournisseur d’hébergement est activée. Les messages ne peuvent pas être échangés entre les deux entreprises tant que cette valeur n’est pas définie sur **True** .
    
      - **EnabledSharedAddressSpace** indique si le fournisseur d’hébergement sera utilisé dans un scénario d’espace d’adresse SIP partagé (domaine fractionné).
        
        > [!NOTE]  
        > Avant de définir <code>EnableSharedAddressSpace</code> sur True, essayez de résoudre l’enregistrement SRV de fédération en interne. S’il est impossible de résoudre cet enregistrement en interne, vous devez créer les enregistrements, _sipfederationtls._tcp.&lt;domaine&gt; et _sip._tls.&lt;domaine&gt; sur le serveur de noms de domaine (DNS). Ces enregistrements doivent pointer vers l’adresse IP externe de l’interface d’accès du serveur Edge.    
      - **HostsOCSUsers** indique si le fournisseur d’hébergement est utilisé pour héberger les comptes Lync Server 2013. Si la valeur est **False** , le fournisseur héberge d’autres types de comptes, comme des comptes Microsoft Exchange.
    
      - **ProxyFQDN** spécifie le nom de domaine complet du serveur proxy utilisé par le fournisseur d’hébergement, dans cet exemple, **proxyserver.fabrikam.com** . Cette valeur ne peut pas être modifiée. Si le fournisseur d’hébergement change de serveur proxy, vous devrez supprimer puis recréer l’entrée pour ce fournisseur.
    
      - **IsLocal** indique si le serveur proxy utilisé par le fournisseur d’hébergement est contenu dans votre topologie Lync Server 2013.
    
      - **VerificationLevel** indique le niveau de vérification autorisé pour les messages à destination et en provenance du fournisseur hébergé. Spécifiez **UseSourceVerification**, qui repose sur le niveau de vérification inclus dans les messages en provenance du fournisseur hébergé. Si ce niveau n’est pas spécifié, le message sera rejeté comme message non vérifiable.

## Voir aussi

#### Tâches

[Exportation de la topologie Lync Server 2013 et copie vers le support externe de l’installation Edge](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)  

#### Concepts

[Vérification de la connectivité entre les serveurs internes et les serveurs Edge dans Lync Server 2013](lync-server-2013-verify-connectivity-between-internal-servers-and-edge-servers.md)  

#### Autres ressources

[New-CsHostingProvider](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsHostingProvider)

