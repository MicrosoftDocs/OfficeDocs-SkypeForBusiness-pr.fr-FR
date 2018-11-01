---
title: 'Lync Server 2013 : Instructions d’intégration de la messagerie unifiée locale'
TOCTitle: Instructions d’intégration de la messagerie unifiée locale et de Lync Server
ms:assetid: 829ac017-6907-40f9-be22-787a28eae0ac
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398656(v=OCS.15)
ms:contentKeyID: 49297919
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Instructions d’intégration de la messagerie unifiée locale et de Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Les instructions suivantes sont des directives et meilleures pratiques à envisager lors du déploiement de Voix Entreprise :

> [!IMPORTANT]  
> La messagerie unifiée Exchange prend en charge IPv6 uniquement si vous utilisez également UCMA 4.

  - Déployez un serveur Lync Server 2013 Standard Edition ou un serveur de pool de serveurs frontaux. Pour plus d’informations sur l’installation, reportez-vous à [Déploiement de Lync Server 2013](lync-server-2013-deploying-lync-server.md) dans la documentation de déploiement.

  - Collaborez avec les administrateurs Exchange pour confirmer les tâches que chacun effectuera afin de garantir une intégration réussie en toute transparence.

  - Déployez les rôles serveur de boîte aux lettres Exchange dans chaque forêt de la messagerie unifiée Exchange où vous souhaitez activer les utilisateurs pour la messagerie unifiée Exchange. Pour plus d’informations sur l’installation des rôles serveur, reportez-vous à la documentation Microsoft Exchange Server 2013.
    
    > [!IMPORTANT]  
    > Lorsque la messagerie unifiée Exchange est installée, elle est configurée de sorte à utiliser un certificat auto-signé.<br />
    Cependant, le certificat auto-signé ne permet à Lync Server 2013 et à la messagerie unifiée Exchange de s’approuver mutuellement, c’est pourquoi il est nécessaire de demander un certificat distinct auprès d’une autorité de certification que les deux serveurs approuvent.

  - Si Lync Server 2013 et la messagerie unifiée Exchange sont installés dans des forêts différentes, configurez chaque forêt Exchange pour approuver la forêt Lync Server 2013 et la forêt Lync Server 2013 pour approuver chaque forêt Exchange. Configurez également les paramètres de la messagerie unifiée Exchange de l’utilisateur sur les objets utilisateurs dans la forêt Lync Server 2013, généralement à l’aide d’un script ou d’un outil inter-forêts tel qu’ILM (Identity Lifecycle Manager).

  - Si nécessaire, installez la console de gestion Exchange pour gérer vos serveurs de messagerie unifiée.

  - Procurez-vous des numéros de téléphone valides pour Outlook Voice Access et le standard automatique.

  - Si vous utilisez une version de la messagerie unifiée Exchange antérieure à Microsoft Exchange Server 2010 Service Pack 1 (SP1), coordonnez les noms pour les plans de numérotation URI SIP de messagerie unifiée Exchange et les plans de numérotation Voix Entreprise.

## Déploiement de serveurs de messagerie unifiée Exchange redondants :

> [!IMPORTANT]  
> Nous vous conseillons de déployer un minimum de deux serveurs sur lesquels les services de messagerie unifiée Exchange s’exécutent pour chaque plan de numérotation URI SIP de messagerie unifiée Exchange que vous configurez pour votre organisation. En plus de fournir une capacité étendue, le déploiement de serveurs redondants offre une disponibilité élevée. En cas de défaillance d’un serveur, Lync Server 2013 peut être configuré pour basculer sur un autre serveur.

Les configurations de l’exemple suivant fournissent la résistance à la messagerie unifiée Exchange.

**Exemple 1 : résistance stance de la messagerie unifiée Exchange**

![Messagerie unifiée Exchange Exemple 1](images/Gg398656.3644b847-0847-4550-a989-e3fc51de5c4b(OCS.15).jpg "Messagerie unifiée Exchange Exemple 1")

Dans l’exemple 1, les serveurs de messagerie unifiée Exchange 1 et 2 sont activés dans le centre de données Tukwila, et les serveurs de messagerie unifiée Exchange 3 et 4 sont activés dans le centre de données Dublin. En cas de défaillance de la messagerie unifiée Exchange dans Tukwila, les enregistrements DNS A pour les serveurs 1 et 2 doivent être configurés respectivement pour pointer sur les serveurs 3 et 4. En cas de défaillance de la messagerie unifiée Exchange dans Dublin, les enregistrements DNS A pour les serveurs 3 et 4 doivent être configurés respectivement pour pointer sur les serveurs 1 et 2.

> [!NOTE]  
> Pour Exemple 1, vous devez également affecter l’un des certificats suivants sur chaque serveur de messagerie unifiée Exchange :<ul>
> <li><p>Utilisez un certificat avec un caractère générique dans l’autre nom du sujet (SAN).</p></li>
> <li><p>Ajoutez le nom de domaine complet de chacun des quatre serveurs de messagerie unifiée Exchange dans l’autre nom du sujet.</p></li></ul>


**Exemple 2 : résistance stance de la messagerie unifiée Exchange**

![Messagerie unifiée Exchange Exemple 2](images/Gg398656.15754273-306e-448d-b258-84bc2936a2e8(OCS.15).jpg "Messagerie unifiée Exchange Exemple 2")

Dans l’exemple 2, dans des conditions de fonctionnement normales, les serveurs de messagerie unifiée Exchange 1 et 2 sont activés dans le centre de données Tukwila, et les serveurs de messagerie unifiée Exchange 3 et 4 sont activés dans le centre de données Dublin. Les quatre serveurs sont tous inclus dans le plan de numérotation URI SIP des utilisateurs Tukwila, toutefois les serveurs 3 et 4 sont désactivés. Dans le cas d’une défaillance d’un serveur de messagerie unifiée Exchange dans Tukwila, par exemple, les serveurs de messagerie unifiée Exchange 1 et 2 doivent être désactivés et les serveurs de messagerie unifiée Exchange 3 et 4 activés afin que le trafic de messagerie unifiée Exchange Tukwila soit acheminé vers les serveurs dans Dublin.

Pour plus d’informations sur l’activation/désactivation de la messagerie unifiée sur Exchange 2013, reportez-vous à « Intégrer la messagerie unifiée Exchange 2013 à Lync Server » à l’adresse [http://go.microsoft.com/fwlink/p/?LinkId=265372](http://go.microsoft.com/fwlink/p/?linkid=265372).

Pour plus d’informations sur l’activation ou la désactivation de la messagerie unifiée sur Microsoft Exchange Server 2010, reportez-vous à :

  - « Activer la messagerie unifiée sur Exchange 2010 » à l’adresse [http://go.microsoft.com/fwlink/p/?LinkId=204418](http://go.microsoft.com/fwlink/p/?linkid=204418).

  - « Désactiver la messagerie unifiée sur Exchange 2010 » à l’adresse [http://go.microsoft.com/fwlink/p/?LinkId=204416](http://go.microsoft.com/fwlink/p/?linkid=204416).

## Voir aussi

#### Concepts

[Processus de déploiement pour l’intégration de la messagerie unifiée locale et de Lync Server 2013](lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md)

