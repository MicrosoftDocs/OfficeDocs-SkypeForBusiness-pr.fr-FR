---
title: 'Lync Server 2013 : Configuration de DNS pour la prise en charge de périphérie'
TOCTitle: Configuration de DNS pour la prise en charge de périphérie
ms:assetid: 955493e6-aa29-424d-bb81-1ef87b3b15e3
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398756(v=OCS.15)
ms:contentKeyID: 49298117
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration de DNS pour la prise en charge de périphérie dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-15_

Vous devez configurer des enregistrements DNS pour les interfaces Edge internes et externes, notamment pour les interfaces des serveurs Edge et proxy inverse. Par défaut, les serveurs Edge ne sont pas joints à un domaine et n’ont pas de nom de domaine complet. Il est fait référence au serveur Edge par un nom court (ordinateur) et non un nom de domaine complet. Cependant, le Générateur de topologie utilise les noms de domaine complets (FQDN) et non des noms courts. Le nom du serveur Edge doit correspondre au nom de domaine complet utilisé par le Générateur de topologie. Pour ce faire, vous définissez un suffixe DNS qui, quand il est associé au nom de l’ordinateur, correspond au nom de domaine complet attendu. Utilisez la procédure suivante de « Pour ajouter le suffixe DNS au nom d’ordinateur du serveur Edge qui n’est pas joint à un domaine » pour ajouter le suffixe DNS au nom de l’ordinateur.

> [!NOTE]  
> Par défaut, DNS utilise un algorithme round robin pour faire tourner l’ordre des données des enregistrements de ressource renvoyées dans les réponses aux requêtes lorsque plusieurs enregistrements de ressource du même type existent pour un nom de domaine DNS interrogé. L’équilibrage de charge DNS de Lync Server 2013 dépend de ce mécanisme. Vérifiez que ce paramètre n’a pas été désactivé. Si vous utilisez un serveur DNS qui n’exécute pas un système d’exploitation Windows, vérifiez que le classement des enregistrements de ressource avec l’algorithme round-robin est activé.

Utilisez les procédures suivantes de «  **Pour créer un enregistrement DNS SRV**  » pour créer et vérifier chaque enregistrement DNS SRV. Utilisez la procédure de «  **Pour créer un enregistrement DNS A**  » pour définir les enregistrements DNS A requis pour l’accès utilisateur externe. Pour confirmer que les enregistrements sont configurés et fonctionnent correctement, reportez-vous à « **Pour vérifier un enregistrement DNS**  » dans cette rubrique. Pour plus d’informations sur chaque enregistrement requis pour prendre en charge l’accès utilisateur externe, reportez-vous à [Détermination de la configuration requise pour DNS pour Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

## Pour ajouter le suffixe DNS au nom de l’ordinateur sur un serveur Edge qui n’est pas joint à un domaine

1.  Sur l’ordinateur, cliquez sur **Démarrer** , cliquez avec le bouton droit sur **Ordinateur** , puis cliquez sur **Propriétés** .

2.  Sous **Paramètres de nom d’ordinateur, de domaine et de groupe de travail** , cliquez sur **Modifier les paramètres** .

3.  Sous l’onglet **Nom de l’ordinateur** , cliquez sur **Modifier** .

4.  Dans **Modification du nom ou du domaine de l’ordinateur** , cliquez sur **Plus** .

5.  Dans **Nom d’ordinateur NetBIOS et suffixe DNS** , dans **Suffixe DNS principal de cet ordinateur** , tapez le nom de votre domaine interne (par exemple, corp.contoso.com), puis cliquez trois fois sur **OK** .

6.  Redémarrez l’ordinateur.

## Pour créer un enregistrement DNS SRV

1.  Sur le serveur DNS approprié, cliquez sur **Démarrer** , sur **Panneau de configuration** , sur **Outils d’administration** , puis sur **DNS** .
    
    > [!IMPORTANT]  
    > Vous devez configurer DNS de façon à avoir : 1) des entrées DNS externes pour les recherches d’enregistrements DNS externes par les utilisateurs distants et les partenaires fédérés ;, 2) des entrées de recherches DNS requises par les serveurs Edge dans le réseau de périmètre (également appelé DMZ, zone démilitarisée et sous-réseau filtré), notamment des enregistrements A pour les serveurs internes exécutant Lync Server 2013 et 3) des entrées DNS internes pour les recherches par les clients internes et les serveurs exécutant Lync Server 2013.

2.  Dans l’arborescence de la console pour le domaine SIP, développez **Zones de recherche directes** , puis cliquez avec le bouton droit sur le domaine dans lequel Lync Server 2013 est installé.

3.  Cliquez sur **Nouveaux enregistrements** .

4.  Dans **Choisissez un type d’enregistrement de ressource** , tapez **Emplacement du service (SRV)** , puis cliquez sur **Créer un enregistrement** .

5.  Fournissez toutes les informations requises pour l’enregistrement DNS SRV.

## Pour créer un enregistrement DNS A

1.  Sur le serveur DNS, cliquez sur **Démarrer** , sur **Panneau de configuration** , sur **Outils d’administration** , puis sur **DNS** .

2.  Dans l’arborescence de la console pour le domaine SIP, développez **Zones de recherche directes** , puis cliquez avec le bouton droit sur le domaine dans lequel Lync Server 2013 est installé.

3.  Cliquez sur **Nouvel hôte (A)** .

4.  Fournissez toutes les informations requises pour l’enregistrement DNS SRV.

## Pour vérifier un enregistrement DNS

1.  Ouvrez une session sur un ordinateur client du domaine.

2.  Cliquez sur **Démarrer** , puis sur **Exécuter** .

3.  Dans la ligne de commande, exécutez la commande suivante :
    
        nslookup <FQDN edge interface>

4.  Vérifiez que vous recevez une réponse résolue en adresse IP appropriée pour le nom de domaine complet.

## Voir aussi

#### Tâches

[Création d’un enregistrement SRV DNS pour l’intégrer à la messagerie unifiée Exchange hébergée](lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md)  

#### Concepts

[Détermination de la configuration requise pour DNS pour Lync Server 2013](lync-server-2013-determine-dns-requirements.md)

