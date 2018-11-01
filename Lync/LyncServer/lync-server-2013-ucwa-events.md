---
title: Événements liés à l’API UCWA
TOCTitle: Événements liés à l’API UCWA
ms:assetid: 26cb409d-f4e4-43c7-873f-b694702d491d
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ945621(v=OCS.15)
ms:contentKeyID: 53095383
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Événements liés à l’API UCWA

 

_**Dernière rubrique modifiée :** 2015-03-09_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync Server 2013 utilise l’API UCWA (Unified Communications Web API) à différentes fins, allant de l’accès à Microsoft Exchange pour effectuer des recherches de contact à la mise à jour des informations de présence pour les clients mobiles.

L’API UCWA écrit les enregistrements liés aux opérations en tant qu’événements de type information, avertissement ou erreur. Le tableau suivant décrit les événements pouvant être écrits par les composants de l’API UCWA.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>ID d’événement</th>
<th>Type d’événement</th>
<th>Résumé</th>
<th>Cause et solution</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>20001</p></td>
<td><p>Information</p></td>
<td><p>API UCWA initialisée</p></td>
<td><p>N/A</p>
<p>N/A</p></td>
</tr>
<tr class="even">
<td><p>20002</p></td>
<td><p>Erreur</p></td>
<td><p>L’API UCWA a rencontré une exception inattendue pendant son initialisation</p></td>
<td><p>Une erreur inattendue s’est produite pendant l’initialisation.</p>
<p>Examinez les détails de l’exception dans l’entrée correspondante du journal des événements pour déterminer la cause possible.</p></td>
</tr>
<tr class="odd">
<td><p>20003</p></td>
<td><p>Erreur</p></td>
<td><p>L’API UCWA a rencontré une exception non traitée.</p></td>
<td><p>Une exception non traitée s’est produite.</p>
<p>Redémarrez le serveur. Si le problème persiste, contactez le support technique.</p></td>
</tr>
<tr class="even">
<td><p>20004</p></td>
<td><p>Erreur</p></td>
<td><p>Impossible d’accéder à Exchange pour la photo HD</p></td>
<td><p>La connexion à Exchange n’est pas disponible.</p>
<p>Vérifiez que la connexion à Exchange est disponible.</p></td>
</tr>
<tr class="odd">
<td><p>20005</p></td>
<td><p>Information</p></td>
<td><p>Récupération de l’échec de l’accès à Exchange pour la photo HD</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="even">
<td><p>20006</p></td>
<td><p>Erreur</p></td>
<td><p>Impossible d’accéder à Exchange pour la recherche de contact</p></td>
<td><p>La connexion à Exchange n’est pas disponible.</p>
<p>Vérifiez que la connexion à Exchange est disponible.</p></td>
</tr>
<tr class="odd">
<td><p>20007</p></td>
<td><p>Information</p></td>
<td><p>Récupération de l’échec de la recherche de contact dans Exchange</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="even">
<td><p>20008</p></td>
<td><p>Avertissement</p></td>
<td><p>Tentative de souscription à un nombre d’abonnements aux informations de présence supérieur au nombre autorisé par application</p></td>
<td><p>Tentative de souscription à un nombre d’abonnements aux informations de présence supérieur au nombre autorisé par application</p>
<p>Vérifiez si les clients possèdent des abonnements superflus</p></td>
</tr>
<tr class="odd">
<td><p>20009</p></td>
<td><p>Avertissement</p></td>
<td><p>Tentative de souscription à un nombre d’abonnements aux informations de présence supérieur au nombre autorisé par lot</p></td>
<td><p>Tentative de souscription à un nombre d’abonnements aux informations de présence supérieur au nombre autorisé par lot</p>
<p>Vérifiez si les clients possèdent des abonnements superflus</p></td>
</tr>
<tr class="even">
<td><p>20010</p></td>
<td><p>Erreur</p></td>
<td><p>Impossible de récupérer les données de la bande entrante</p></td>
<td><p>Impossible de récupérer les données de la bande entrante</p>
<p>Si le problème persiste, contactez le support technique</p></td>
</tr>
<tr class="odd">
<td><p>20011</p></td>
<td><p>Erreur</p></td>
<td><p>Impossible de s’abonner aux informations de présence</p></td>
<td><p>Impossible de s’abonner aux informations de présence</p>
<p>Si le problème persiste, contactez le support technique</p></td>
</tr>
<tr class="even">
<td><p>20012</p></td>
<td><p>Erreur</p></td>
<td><p>Échec de l’enregistrement du point de terminaison</p></td>
<td><p>Échec de l’enregistrement du point de terminaison</p>
<p>Si le problème persiste, contactez le support technique</p></td>
</tr>
<tr class="odd">
<td><p>20013</p></td>
<td><p>Erreur</p></td>
<td><p>Le MCU de messagerie instantanée n’est pas disponible.</p></td>
<td><p>Le MCU de messagerie instantanée n’est pas disponible.</p>
<p>Vérifiez si le MCU de messagerie instantanée est en cours d’exécution.</p></td>
</tr>
<tr class="even">
<td><p>20014</p></td>
<td><p>Information</p></td>
<td><p>Récupération de l’échec de la connexion au MCU de messagerie instantanée</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="odd">
<td><p>20015</p></td>
<td><p>Erreur</p></td>
<td><p>Le MCU AV n’est pas disponible.</p></td>
<td><p>Le MCU AV n’est pas disponible.</p>
<p>Vérifiez si le MCU AV est en cours d’exécution.</p></td>
</tr>
<tr class="even">
<td><p>20016</p></td>
<td><p>Information</p></td>
<td><p>Récupération de l’échec de la connexion au MCU AV</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="odd">
<td><p>20017</p></td>
<td><p>Erreur</p></td>
<td><p>Le MCU AS n’est pas disponible.</p></td>
<td><p>Le MCU AS n’est pas disponible.</p>
<p>Vérifiez si le MCU AS est en cours d’exécution.</p></td>
</tr>
<tr class="even">
<td><p>20018</p></td>
<td><p>Information</p></td>
<td><p>Récupération de l’échec de la connexion au MCU AS</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="odd">
<td><p>20019</p></td>
<td><p>Erreur</p></td>
<td><p>Le MCU de données n’est pas disponible.</p></td>
<td><p>Le MCU de données n’est pas disponible.</p>
<p>Vérifiez si le MCU de données est en cours d’exécution.</p></td>
</tr>
<tr class="even">
<td><p>20020</p></td>
<td><p>Information</p></td>
<td><p>Récupération de l’échec de la connexion au MCU de données</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="odd">
<td><p>20021</p></td>
<td><p>Erreur</p></td>
<td><p>Impossible de rejoindre le MCU de messagerie instantanée</p></td>
<td><p>Impossible de rejoindre le MCU de messagerie instantanée</p>
<p>Vérifiez si le MCU de messagerie instantanée est en cours d’exécution.</p></td>
</tr>
<tr class="even">
<td><p>20022</p></td>
<td><p>Erreur</p></td>
<td><p>Impossible de rejoindre le MCU AV</p></td>
<td><p>Impossible de rejoindre le MCU AV</p>
<p>Vérifiez si le MCU AV est en cours d’exécution.</p></td>
</tr>
<tr class="odd">
<td><p>20023</p></td>
<td><p>Erreur</p></td>
<td><p>Impossible de rejoindre le MCU AS</p></td>
<td><p>Impossible de rejoindre le MCU AS</p>
<p>Vérifiez si le MCU AS est en cours d’exécution.</p></td>
</tr>
<tr class="even">
<td><p>20024</p></td>
<td><p>Erreur</p></td>
<td><p>Impossible de rejoindre le MCU de données</p></td>
<td><p>Impossible de rejoindre le MCU de données</p>
<p>Vérifiez si le MCU de données est en cours d’exécution.</p></td>
</tr>
<tr class="odd">
<td><p>20025</p></td>
<td><p>Erreur</p></td>
<td><p>Impossible d’accéder à Active Directory pour la photo</p></td>
<td><p>La connexion à Active Directory n’est pas disponible.</p>
<p>Vérifiez que la connexion à Active Directory est disponible.</p></td>
</tr>
<tr class="even">
<td><p>20026</p></td>
<td><p>Information</p></td>
<td><p>Récupération de l’échec de l’accès à Active Directory pour la photo</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="odd">
<td><p>20027</p></td>
<td><p>Avertissement</p></td>
<td><p>Impossible d’effectuer la désérialisation</p></td>
<td><p>Impossible d’effectuer la désérialisation</p>
<p>Si le problème persiste, contactez le support technique.</p></td>
</tr>
</tbody>
</table>

