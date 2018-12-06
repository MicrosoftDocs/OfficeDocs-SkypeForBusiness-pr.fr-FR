---
title: "Conf. d’un nœud obs. pour l’exécution des transactions synthétiques"
TOCtitle: "Conf. d’un nœud obs. pour l’exécution des transactions synthétiques"
ms:assetid: cedda508-8881-4079-88d5-49798f342ddf
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205314(v=OCS.15)
ms:contentKeyID: 49298872
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration d’un nœud observateur pour l’exécution des transactions synthétiques

 

_**Dernière rubrique modifiée :** 2015-03-09_

Une fois les fichiers de l’agent System Center installés, vous devez configurer le nœud observateur. La procédure varie selon que l’ordinateur du nœud observateur se trouve à l’intérieur ou à l’extérieur de votre réseau de périphérie.

Lorsque vous configurez un nœud observateur, vous devez également choisir le type de méthode d’authentification utilisé par ce nœud. Lync Server 2013 vous permet de choisir une ou deux méthodes d’authentification : serveur approuvé ou authentification des informations d’identification. Les différences entre ces deux méthodes sont indiquées dans le tableau suivant :


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Configuration</th>
<th>Description</th>
<th>Emplacements pris en charge</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Serveur approuvé</p></td>
<td><p>Utilise un certificat pour emprunter l’identité d’un serveur interne et contourner les demandes d’authentification.</p>
<p>Utile pour les administrateurs qui préfèrent gérer un seul certificat au lieu de plusieurs mots de passe d’utilisateur sur chaque nœud observateur.</p></td>
<td><p>Au sein de l’entreprise.</p>
<p>Notez qu’avec cette méthode, le nœud observateur doit se trouver dans le même domaine que les pools surveillés. Si le nœud observateur et les pools surveillés se trouvent dans des domaines différents, utilisez l’authentification des informations d’identification à la place.</p></td>
</tr>
<tr class="even">
<td><p>Authentification des informations d’identification</p></td>
<td><p>Stocke les noms d’utilisateur et mots de passe de manière sécurisée dans le Gestionnaire d’informations d’identification Windows sur chaque nœud observateur.</p>
<p>Ce mode implique davantage d’opérations de gestion des mots de passe, mais est la seule option pour les nœuds observateurs situés en dehors de l’entreprise. Ces nœuds observateurs ne peuvent pas être traités comme un point de terminaison approuvé pour l’authentification.</p></td>
<td><p>En dehors de l’entreprise.</p>
<p>Au sein de l’entreprise.</p></td>
</tr>
</tbody>
</table>


Vous devez aussi vérifier que votre pare-feu présente des règles de trafic entrant pour MonitoringHost.exe et PowerShell.exe. Si ces deux processus sont bloqués par le pare-feu, alors vos transactions synthétiques échoueront avec une erreur 504 (expiration serveur).

