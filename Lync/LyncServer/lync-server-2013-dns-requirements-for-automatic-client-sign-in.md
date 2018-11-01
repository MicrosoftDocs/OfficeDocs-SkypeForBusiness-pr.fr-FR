---
title: "Enr. DNS requis pour la connexion auto. des clients dans Lync Server 2013"
TOCtitle: "Enr. DNS requis pour la connexion auto. des clients dans Lync Server 2013"
ms:assetid: 3bcd4bb3-a022-4ffa-b005-1a95ad2b1796
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425884(v=OCS.15)
ms:contentKeyID: 49296945
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Enregistrements DNS requis pour la connexion automatique des clients dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Cette section décrit les enregistrements DNS (Domain Name System) nécessaires à la connexion automatique des clients. Quand vous déployez vos serveurs Standard Edition ou pools frontaux, vous pouvez configurer vos clients pour qu’ils utilisent la détection automatique pour se connecter au serveur Standard Edition ou pool frontal approprié. Si vous envisagez un mode de connexion manuel de vos clients à Lync Server 2013, vous pouvez ignorer cette rubrique.

Pour prendre en charge la connexion automatique des clients, vous devez :

  - désigner un seul serveur ou pool pour distribuer et authentifier les demandes de connexion de client. Il peut s’agir d’un serveur ou pool de votre organisation qui héberge des utilisateurs. Vous pouvez également désigner un serveur ou un pool dédié n’hébergeant aucun utilisateur. La désignation d’un pool frontal est conseillée, car elle permet d’optimiser la disponibilité.

  - créer un enregistrement DNS SRV interne devant prendre en charge la connexion automatique des clients pour ce serveur ou ce pool.
    
    > [!NOTE]  
    > Dans les exigences d’enregistrement suivantes, le domaine SIP fait référence à la partie hôte des URI SIP attribuée aux utilisateurs. Par exemple, si les URL SIP possèdent le format *@contoso.com, le domaine SIP est contoso.com. Le domaine SIP est souvent différent du domaine Active Directory interne. Une organisation peut également prendre en charge plusieurs domaines SIP.

Pour autoriser la configuration automatique des clients, vous devez créer un enregistrement SRV DNS interne associant l’un des enregistrements suivants au nom de domaine complet du pool frontal ou du serveur Standard Edition qui distribue les demandes de connexion émises à partir des clients Lync :

  - \_sipinternaltls.\_tcp.*\<domaine\>* : pour les connexions TLS internes

Vous devez créer un seul enregistrement SRV pour le pool frontal ou le serveur Standard Edition qui distribuera les demandes de connexion.

Le tableau suivant contient quelques exemples d’enregistrements requis pour la société fictive Contoso qui prend en charge les domaines SIP de contoso.com et retail.contoso.com.

### Exemples d’enregistrements DNS requis pour la connexion automatique des clients sur plusieurs domaines SIP

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nom de domaine complet du pool frontal utilisé pour distribuer les demandes de connexion</th>
<th>Domaine SIP</th>
<th>Enregistrement SRV DNS</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>pool01.contoso.com</p></td>
<td><p>contoso.com</p></td>
<td><p>Enregistrement SRV pour le domaine _sipinternaltls._tcp.contoso.com via le port 5061 qui mappe sur pool01.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>pool01.contoso.com</p></td>
<td><p>retail.contoso.com</p></td>
<td><p>Enregistrement SRV pour le domaine _sipinternaltls._tcp.retail.contoso.com via le port 5061 qui mappe sur pool01.contoso.com</p></td>
</tr>
</tbody>
</table>


> [!NOTE]  
> Par défaut, les requêtes portant sur des enregistrements DNS exigent une correspondance exacte entre le domaine indiqué dans le nom de l’utilisateur et l’enregistrement SRV. Si vous préférez que les requêtes DNS clientes utilisent la correspondance de suffixe, vous pouvez configurer la stratégie de groupe DisableStrictDNSNaming. Pour plus d’informations, voir <a href="lync-server-2013-planning-for-clients-and-devices.md">Planification des clients et périphériques dans Lync Server 2013</a> dans la documentation de planification.

## Exemples de certificats et d’enregistrements DNS requis pour la connexion automatique des clients

Cet exemple reprend les exemples du tableau précédent. L’organisation Contoso prend en charge les domaines SIP de contoso.com et retail.contoso.com, et tous ses utilisateurs ont un URI SIP de l’une des formes suivantes :

  - *\<utilisateur\>*@retail.contoso.com

  - *\<utilisateur\>*@contoso.com

