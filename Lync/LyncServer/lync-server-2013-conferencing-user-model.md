---
title: Modèle d’utilisateur de conférence
TOCTitle: Modèle d’utilisateur de conférence
ms:assetid: ba4bbba9-f2e3-4cab-8eba-b51f12133cab
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205199(v=OCS.15)
ms:contentKeyID: 49298669
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Modèle d’utilisateur de conférence

 

_**Dernière rubrique modifiée :** 2012-10-22_

La taille des réunions constitue un élément essentiel du modèle utilisateur des conférences Lync Server. Après avoir collecté des données à partir de plusieurs points de données (comme indiqué dans la section précédente), nous avons déterminé les points suivants :

  - La plupart des réunions sont en fait de petites réunions collaboratives, avec une moyenne de quatre à six participants.

  - Environ 80 % des réunions comptent moins de 20 participants.

  - 99,98 % des réunions comptent moins de 100 participants.

Outre la taille des réunions, le modèle utilisateur des conférences prend également en compte divers facteurs, tels que les suivants :

  - **Réunions simultanées**   Combien d’utilisateurs devraient participer simultanément à des réunions ?

  - **Mélange de médias**   Quels types de médias sont disponibles et susceptibles d’être utilisés par les utilisateurs lors des réunions ?

  - **Types d’utilisateurs**   Les utilisateurs sont-ils internes, distants, fédérés ou anonymes ?

  - **Temps d’accès aux réunions**   Combien de temps faut-il pour que tous les utilisateurs d’une réunion rejoignent une réunion ?

Pour plus d’informations sur le modèle utilisateur, voir [Modèles utilisateur dans Lync Server 2013](lync-server-2013-user-models.md).

Pour déterminer le nombre de réunions et d’utilisateurs à utiliser pour effectuer les tests, nous avons procédé comme suit :

  - Nous avons pris le nombre total d’utilisateurs d’une organisation (par exemple, 80 000 utilisateurs) que nous avons multiplié par le taux de simultanéité des réunions (par exemple, 5 % de tous les utilisateurs) afin de déterminer le nombre total d’utilisateurs susceptibles d’assister simultanément à des réunions (dans le présent exemple, 4 000 utilisateurs).

  - Nous avons divisé le nombre total d’utilisateurs par le nombre de serveurs frontauxLync Server 2013 du déploiement (par exemple, 8 serveurs) afin de déterminer une estimation du nombre de participants à une réunion par serveur frontal (dans le présent exemple, 500 utilisateurs par serveur frontal).

  - Nous avons divisé le nombre d’utilisateurs par serveur frontal par la taille moyenne des réunions (par exemple, 4 utilisateurs) afin de déterminer une estimation du nombre moyen de réunions par serveur frontal (dans le présent exemple, 125 réunions par serveur frontal).

  - Pour obtenir la charge par média sur chaque serveur frontal, nous avons calculé une estimation du mélange de médias. Par exemple, en supposant que 75 % des réunions requièrent plus qu’un simple support audio et que 50 % de ces réunions requièrent un partage d’application, 47 réunions et 188 utilisateurs en moyenne se connectent simultanément à chaque serveur frontal pour un partage d’application.

  - Nous avons testé diverses tailles de réunion (en nous basant sur notre modèle utilisateur qui compte un maximum de 250 utilisateurs dans un pool partagé) afin de garantir l’extensibilité du serveur.

