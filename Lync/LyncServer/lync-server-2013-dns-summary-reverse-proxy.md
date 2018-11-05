---
title: 'Lync Server 2013 : Résumé DNS - Proxy inverse'
TOCTitle: Résumé DNS - Proxy inverse
ms:assetid: 3073affa-4d92-4453-9974-3a82ca0c6445
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204781(v=OCS.15)
ms:contentKeyID: 49296769
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Résumé DNS - Proxy inverse dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Vous configurez deux cartes réseau dans votre serveur proxy inverse comme suit :

## Cartes réseau de proxy inverse requises

  - **Carte réseau 1 (interface interne)** (exemple)
    
    Interface interne avec 172.25.33.40 affecté.
    
    Aucune passerelle par défaut n’est définie.
    
    Assurez-vous qu’il existe un itinéraire entre le réseau contenant l’interface interne du serveur proxy inverse et les réseaux qui contiennent des serveurs d’un pool de serveurs frontauxLync Server (par exemple, de 172.25.33.0 à 192.168.10.0).

  - **Carte réseau 2 (interface externe)** (exemple)
    
    Au moins une adresse IP publique est affectée à cette carte réseau.
    
    La passerelle est définie de sorte à pointer sur le routeur ou le pare-feu intégré de votre périmètre extérieur. (10.45.16.1 dans les exemples de scénario)

### Enregistrements DNS requis pour le proxy inverse

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Emplacement/TYPE/Port</th>
<th>FQDN</th>
<th>Adresse IP</th>
<th>Mappage à/commentaires</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS externe/A</p></td>
<td><p>webext.contoso.com</p></td>
<td><p>Écouteur affecté pour les ressources publiées à l’extérieur</p></td>
<td><p>Services web externes à partir du déploiement interne. Des enregistrements supplémentaires peuvent être définis et créés pour tous les pools et les serveurs uniques de tous les domaines SIP qui utilisent ce proxy inverse et qui ont défini des services web externes.</p></td>
</tr>
<tr class="even">
<td><p>DNS externe/A</p></td>
<td><p>webdirext.contoso.com</p></td>
<td><p>Écouteur affecté pour les ressources publiées à l’extérieur</p></td>
<td><p>Services web externes pour les directeurs ou les pools de directeurs de votre déploiement. Vous pouvez définir autant de directeurs qu’il y a de directeurs distincts, parmi lesquels certains peuvent être associés à d’autres domaines SIP.</p>

> [!IMPORTANT]  
> La définition des enregistrements DNS et la publication des directeurs n’est une décision imputable ni au pool de serveurs frontaux, ni au directeur. Vous devez définir et publier à la fois le directeur et les services web externes du pool de serveurs frontaux si vous utilisez des directeurs. Des types de trafic spécifiques (pour l’authentification et autres utilisations) seront envoyés d’abord au directeur, si cela est défini dans la topologie.

</td>
</tr>
<tr class="odd">
<td><p>DNS externe/A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>Écouteur affecté pour les ressources publiées à l’extérieur</p></td>
<td><p>Conférences rendez-vous publiées en externe</p></td>
</tr>
<tr class="even">
<td><p>DNS externe/A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>Écouteur affecté pour les ressources publiées à l’extérieur</p></td>
<td><p>Conférences publiées en externe</p></td>
</tr>
<tr class="odd">
<td><p>DNS externe/A</p></td>
<td><p>officewebapps01.contoso.com</p></td>
<td><p>Écouteur affecté pour Office Web Apps Server</p></td>
<td><p>Office Web Apps Server déployé de manière interne ou dans le périmètre et publié pour l’accès client externe</p></td>
</tr>
<tr class="even">
<td><p>DNS externe/A</p></td>
<td><p>lyncdiscover.contoso.com</p></td>
<td><p>Écouteur affecté pour les ressources publiées à l’extérieur</p></td>
<td><p>Enregistrement externe de découverte Lync pour la découverte automatique en externe, notamment la mobilité, Microsoft Lync Web App et Scheduler Web App</p></td>
</tr>
</tbody>
</table>

