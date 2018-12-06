---
title: 'Lync Server 2013 : Création et vérification des enregistrements SRV DNS'
TOCTitle: Création et vérification des enregistrements SRV DNS
ms:assetid: 86888c7e-1401-458f-9a7b-08ac726deeec
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398680(v=OCS.15)
ms:contentKeyID: 49297960
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Création et vérification des enregistrements SRV DNS dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-21_

Pour effectuer correctement cette procédure, vous devez être connecté au serveur ou au domaine au moins en tant que membre du groupe Administrateurs du domaine ou du groupe DnsAdmins.

Cette rubrique explique comment configurer les enregistrements DNS que vous devez créer dans les déploiements Lync Server 2013, ainsi que ceux requis pour la connexion client automatique. Lorsque vous générez un pool de serveurs frontaux, le programme (d’installation créedes objets et paramètres Active Directory pour le pool, notamment le nom de domaine complet (FQDN) de ce dernier. Des objets et paramères similaires sont créés pour un serveur Standard Edition. Afin que les clients puissent se connecter au pool ou au serveur Standard Edition, le FQDN du pool ou du serveur Standard Edition doit être enregistré dans DNS. Vous devez créer des enregistrements SRV DNS sur votre serveur DNS interne pour chaque domaine SIP. Cette procédure suppose que ce serveur comporte plusieurs zones pour vos domaines d’utilisateurs SIP.

## Pour configurer un enregistrement DNS SRV

1.  Sur le serveur DNS, cliquez sur **Démarrer** , sur **Outils d’administration** , puis sur **DNS** .

2.  Dans l’arborescence de la console pour votre domaine SIP, développez **Zones de recherche directes** , puis cliquez avec le bouton droit sur le domaine SIP dans lequel Lync Server 2013 sera installé.

3.  Cliquez sur **Nouveaux enregistrements** .

4.  Dans **Choisissez un type d’enregistrement de ressource** , cliquez sur **Emplacement du service (SRV)** , puis sur **Créer un enregistrement** .

5.  Cliquez sur **Service** , puis tapez **\_sipinternaltls** .

6.  Cliquez sur **Protocole** , puis tapez **\_tcp** .

7.  Cliquez sur **Numéro de port** , puis tapez **5061** .

8.  Cliquez sur **Hôte offrant ce service** , puis tapez le nom de domaine complet du pool ou du serveur Standard Edition.

9.  Cliquez sur **OK** , puis sur **Terminé** .

## Pour vérifier la création d’un enregistrement DNS SRV

1.  Ouvrez une session sur un ordinateur client du domaine dont le compte est membre du groupe Utilisateurs authentifiés ou qui dispose des autorisations équivalentes.

2.  Cliquez sur **Démarrer** , puis sur **Exécuter** .

3.  Dans la zone **Ouvrir** , tapez **cmd** , puis cliquez sur **OK** .

4.  Dans l’invite de commandes, tapez **nslookup** , puis appuyez sur Entrée.

5.  Tapez **set type=srv** , puis appuyez sur Entrée.

6.  Tapez **\_sipinternaltls.\_tcp.contoso.com** , puis appuyez sur Entrée. Le résultat obtenu pour l’enregistrement TLS (Transport Layer Security, sécurité de la couche de transport) est le suivant :
    
    Serveur : *\<serveur dns\>* .contoso.com
    
    Adresse : *\<adresse IP du serveur DNS\>*
    
    Réponse ne faisant pas autorité :
    
    Emplacement du service SRV \_sipinternaltls.\_tcp.contoso.com :
    
    priorité = 0
    
    poids = 0
    
    port = 5061
    
    nom d’hôte du serveur = nompool.contoso.com (ou enregistrement A du serveur Standard Edition)
    
    poolname.contoso.com adresse internet = *\<adresse IP virtuelle de l’équilibreur de charge\>* ou *\<adresse IP d’un serveur Enterprise Edition pour les pools avec un serveur Enterprise Edition\>* ou *\<adresse IP du serveur Standard Edition\>*

7.  Lorsque vous avez terminé, dans l’invite de commandes, tapez **exit** et appuyez sur Entrée.

## Pour vérifier que le nom de domaine complet du pool frontal ou du serveur Standard Edition peut être résolu

1.  Ouvrez une session sur un ordinateur client du domaine.

2.  Cliquez sur **Démarrer** , puis sur **Exécuter** .

3.  Dans la zone **Ouvrir** , tapez **cmd** , puis cliquez sur **OK** .

4.  Dans l’invite de commandes, tapez **nslookup** *\<nom de domaine complet du pool frontal\>* ou *\<nom de domaine complet du serveur Standard Edition\>* et appuyez sur Entrée.

5.  Vérifiez que vous recevez une réponse résolue en adresse IP appropriée pour le nom de domaine complet.

