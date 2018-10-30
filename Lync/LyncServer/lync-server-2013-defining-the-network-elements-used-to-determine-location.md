---
title: "Lync Server 2013 : Déf. éléments réseau utilisés pour déterminer l’emplacement"
TOCTitle: Définition des éléments réseau utilisés pour déterminer l’emplacement
ms:assetid: 7538779d-055d-44ed-8dd7-11c45fc1b9f5
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398567(v=OCS.15)
ms:contentKeyID: 49297753
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Définition des éléments réseau utilisés pour déterminer l’emplacement dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-29_

Si vous configurez votre infrastructure Lync Server pour la prise en charge de la détection automatique de l’emplacement du client, vous devez d’abord déterminer quels éléments réseau utiliser pour mettre en correspondance les appelants et les emplacements. Dans Lync Server 2013, vous pouvez associer les éléments réseau de couche 2 et 3 suivants avec des emplacements :

  - Adresses BSSID (Basic Service Set Identification) des points d’accès sans fil (WAP) (couche 2)

  - Port commuté LLDP (couche 2)

  - ID de châssis commuté LLDP (couche 2)

  - Sous-réseaux IP (couche 3)

  - Adresses MAC des clients (couche 2)

Les éléments réseau sont répertoriés par ordre de priorité. Si un client peut être localisé en utilisant plusieurs éléments réseau, Lync Server utilise l’ordre de priorité pour déterminer quel mécanisme utiliser.

Les sections suivantes abordent plus en détail l’utilisation de chaque élément réseau.

> [!IMPORTANT]  
> Lorsque vous utilisez des éléments réseau pour mettre en correspondance les appelants avec les emplacements, il est très important de maintenir la base de données du service d’informations sur l’emplacement à jour. Par exemple, si vous ajoutez ou modifiez un élément réseau, comme un point d’accès sans fil, vous devez supprimer l’ancienne entrée et ajouter la nouvelle entrée dans la base de données d’emplacements.

## Point d’accès sans fil

Lorsqu’un client se connecte au réseau via une liaison sans fil, la demande d’emplacement utilise l’adresse BSSID du point d’accès sans fil pour déterminer son emplacement. Si le client est en déplacement, le point d’accès sans fil indiqué risque de ne pas être le plus proche et il est même possible de sélectionner un point d’accès sans fil se trouvant à un autre étage du bâtiment. Pour indiquer que l’emplacement est approximatif, vous pouvez ajouter à la valeur de l’emplacement le descripteur Near ou Close to.

Cette méthode d’emplacement part du principe que le BSSID de chaque point d’accès sans fil est statique. Cependant, si votre fournisseur de points d’accès sans fil utilise des BSSID attribués de manière dynamique, le BSSID obtenu auprès d’un point d’accès sans fil peut changer (cela peut se produire suite à une modification de configuration du point d’accès), et les clients sans fil peuvent se retrouver en situation de ne pas recevoir d’emplacement. Pour empêcher cette éventualité, vous devez renseigner la base de données du service d’informations sur l’emplacement à l’aide d’ERL pour toutes les adresses BSSID possibles utilisées par chaque point d’accès sans fil.

## Ports et commutateurs LLDP

Les commutateurs Ethernet gérés qui prennent en charge le protocole LLDP-MED (Link Layer Discovery Protocol-Media Endpoint Discover) peuvent annoncer leur identité et leurs informations de port aux clients compatibles LLDP-MED, lesquelles peuvent alors faire l’objet d’une requête dans la base de données d’emplacements afin de fournir l’emplacement du périphérique. Vous pouvez associer des ERL uniquement sur l’ID du châssis commuté, ou les mapper au niveau du port.

> [!NOTE]  
> Lync Server 2013 prend en charge l’utilisation de LLDP-MED pour déterminer uniquement les emplacements des périphériques Lync Phone Edition et Lync 2013 en cours d’exécution sur Windows 8. Si vous avez besoin d’utiliser des données de couche 2 au niveau du commutateur pour déterminer l’emplacement d’autres clients Lync basés sur ordinateur câblé, vous devez utiliser la méthode de l’adresse MAC du client.

## Sous-réseau

Les sous-réseaux IP de couche 3 fournissent un mécanisme pris en charge par tous les clients Lync Server qui permet de détecter automatiquement l’emplacement du client. L’utilisation de sous-réseaux IP constitue la méthode d’emplacement la plus simple pour configurer et gérer des clients câblés. Avant d’opter pour l’utilisation de sous-réseaux, en revanche, répondez aux questions suivantes pour déterminer si la spécificité de l’emplacement du sous-réseau est suffisamment fine pour rechercher un client avec précision :

  - Un ou plusieurs sous-réseaux des clients couvrent-ils plusieurs étages ?

  - Un ou plusieurs sous-réseaux couvrent-t-ils plusieurs immeubles ?

  - Quelle est la surface couverte par chaque sous-réseau client ?

Si le sous-réseau couvre une zone trop vaste, vous devrez envisager d’utiliser un autre mécanisme pour rechercher les clients. Cependant, si possible, nous recommandons aux clients de réorganiser leur sous-réseau IP afin de respecter les exigences de spécificité d’emplacement ERL plutôt que d’induire le coût et la complexité des solutions SNMP tierces.

## Adresse MAC d’un client

Pour utiliser l’adresse MAC d’un ordinateur client pour rechercher un appelant, vous avez besoin de commutateurs Ethernet gérés, et vous devez déployer une solution SNMP tierce capable de découvrir les adresses MAC des clients Lync connectés à (ou via) ces commutateurs. La solution SNMP interroge continuellement les commutateurs gérés pour obtenir les mappages actuels des adresses MAC de point de terminaison connectées à chaque port et obtient les IP de port correspondants. Pendant la demande d’un client Lync au service d’informations sur l’emplacement, le service d’informations sur l’emplacement interroge l’application tierce à l’aide de l’adresse MAC du client, puis renvoie les adresses IP et ID de port d’un commutateur correspondant. Le service d’informations sur l’emplacement utilise ces informations pour interroger son schéma de câblage de couche 2 publié afin d’obtenir un enregistrement correspondant et renvoie l’emplacement au client. Si vous utilisez cette option, vérifiez que les identifiants de port de commutateur sont cohérents entre l’application SNMP et les enregistrements de la base de données d’emplacements publiés.

> [!NOTE]  
> Certaines solutions SNMP tierces peuvent prendre en charge les commutateurs d’accès non gérés ; si le commutateur qui dessert le client Lync est non géré mais comporte une liaison montante vers un commutateur de distribution géré, le commutateur géré peut signaler à l’application SNMP les adresses MAC des clients connectés au commutateur d’accès. Ces informations permettent au service d’informations sur l’emplacement d’identifier l’emplacement de l’utilisateur. Cependant, il est possible d’affecter un seul ERL à tous les ports sur le commutateur non géré afin que la spécificité de l’emplacement soit disponible uniquement au niveau du châssis du commutateur d’accès, et non au niveau du port.
