---
title: Modification du diagramme de configuration du réseau dans Lync Server 2013
TOCTitle: Modification du diagramme de configuration du réseau dans Lync Server 2013
ms:assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg558643(v=OCS.15)
ms:contentKeyID: 53095406
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Modification du diagramme de configuration du réseau dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-21_

La majeure partie du travail qu’un concepteur effectue dans l’outil de planification Lync Server 2013 consiste à définir les entrées pour les adresses IP et les noms de domaine complets (FQDN) des entrées dans le diagramme de réseau. Les informations entrées dans cette page sont utilisées dans les rapports et dans d’autres données contenues dans l’outil de planification.

![Outil de planification - Diagramme réseau](images/Gg558643.eeabee2d-698c-4b79-baa5-caa4cfb7edb3(OCS.15).jpg "Outil de planification - Diagramme réseau")

L’outil de planification crée un diagramme de réseau avec un texte par défaut pour les adresses IP et les noms de domaine complets (FQDN).

Pour modifier le diagramme de réseau et les valeurs entrées :

1.  Commencez par choisir une section du réseau. Par exemple, double-cliquez sur le texte **access1.contoso.com**. Dans la boîte de dialogue qui s’ouvre, tapez le nom de domaine complet (FQDN) réel du serveur access1.contoso.com et l’adresse IP réelle, en remplaçant 131.107.155.3.

2.  Cliquez sur **OK** pour enregistrer les entrées.

3.  Continuez à modifier les adresses IP et les noms de domaine complets (FQDN) en spécifiant des adresses IP virtuelles pour les programmes d’équilibrage de la charge matérielle ou des entrées de serveur pour l’équilibrage de la charge DNS des serveurs contenus dans les pools.

Une fonction utile de l’outil de planification est la possibilité d’affecter une plage d’adresses IP et de noms d’hôte de serveur, au lieu de demander au concepteur de modifier chaque serveur d’un pool. Par exemple :

1.  Double-cliquez sur les serveurs frontaux du pool. Quand la boîte de dialogue s’ouvre, sélectionnez **Souhaitez-vous utiliser les adresses IP et les noms de domaine complets (FQDN) comme points de départ pour tous les serveurs équivalents dans ce cluster ?**.

2.  Dans l’exemple, la valeur de démarrage pour le premier serveur est fe0101.contoso.com avec l’adresse IP 192.168.21.122.

3.  Tapez **fe0.contoso.com** dans **Nom de domaine complet (FQDN) du serveur frontal**, tapez **192.168.21.131** dans **Adresse IP du serveur frontal**, puis cliquez sur **OK**.

4.  La fonction d’incrémentation automatique met à jour tous les serveurs du pool entre fe01 et fe06, et toutes les adresses IP entre 192.168.21.131 et 136.

Une fois toutes les modifications terminées, enregistrez la topologie en procédant comme suit :

Pour enregistrer la conception de l’outil de planification, cliquez sur **Fichier**, puis sur **Enregistrer la topologie** ou **Enregistrer la topologie sous**. Si une boîte de dialogue **Enregistrer l’outil de planification sous le nom** s’affiche, tapez un nom pour le fichier dans **Nom du fichier**, puis cliquez sur **Enregistrer**.

## Voir aussi

#### Concepts

[Modification de la conception dans Lync Server 2013](lync-server-2013-editing-the-design.md)

