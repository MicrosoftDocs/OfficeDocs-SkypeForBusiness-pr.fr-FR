---
title: "Transition d’un serv. de méd. colocalisé vers un serv. de méd. aut. (facult.)"
TOCtitle: "Transition d’un serv. de méd. colocalisé vers un serv. de méd. aut. (facult.)"
ms:assetid: 7c3c2fb4-4ff2-47b1-aab3-0aa91472eadb
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205026(v=OCS.15)
ms:contentKeyID: 49297849
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Transition d’un serveur de médiation colocalisé vers un serveur de médiation autonome (facultatif)

 

_**Dernière rubrique modifiée :** 2012-10-19_

Appliquez la procédure qui suit pour effectuer la transition de votre serveur de médiation, colocalisé sur votre serveur Standard Edition ou pool frontal, vers un serveur de médiation autonome pour un déploiement sur un seul site.

## Pour passer d’un serveur de médiation colocalisé à un serveur de médiation autonome

1.  Ouvrez une topologie existante à partir du générateur de topologie.

2.  Dans le volet gauche, naviguez jusqu’à **Pools de médiation** .

3.  Cliquez avec le bouton droit sur **Pools de médiation** , puis cliquez sur **Nouveau serveur de médiation** .

4.  Dans la page **Définir un nouveau pool de médiation** , spécifiez le nom de domaine complet du nouveau pool de serveurs de médiation. Indiquez également s’il s’agit d’un pool de serveur unique ou de plusieurs serveurs, puis cliquez sur **Suivant** .

5.  Sélectionnez le pool de serveurs frontaux du tronçon suivant vers lequel le nouveau serveur de médiation acheminera les appels entrants, puis cliquez sur **Suivant** .

6.  Sélectionnez le pool Edge que doit utiliser le serveur de médiation, puis cliquez sur **Suivant** .

7.  Dans la page **Spécifier des passerelles RTC** , associez la passerelle RTC précédente au serveur de médiation. Sélectionnez la passerelle, puis cliquez sur **Ajouter** .

8.  Cliquez sur **Terminer** pour fermer l’Assistant **Définir un nouveau pool de médiation** .

9.  Dans le **Générateur de topologie** , sélectionnez le nœud supérieur **Lync Server 2013**.

10. Dans le volet **Actions** , sélectionnez **Publier la topologie** et terminez l’Assistant.

11. Suivez les étapes décrites dans [Installation des fichiers du serveur de médiation dans Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) de la documentation de déploiement pour installer les fichiers sur le nouveau serveur de médiation.

12. Une fois les fichiers installés sur le serveur de médiation, revenez dans le générateur de topologie et, dans le volet gauche, accédez au pool.

13. Cliquez avec le bouton droit sur le pool et sélectionnez **Modifier les propriétés** .

14. Sous **Serveur de médiation** , décochez la case **Activation de la fonctionnalité de cohabitation du serveur de médiation** , puis cliquez sur **OK** .

15. Dans le **Générateur de topologie** , sélectionnez le nœud supérieur **Lync Server 2013**.

16. Dans le menu **Action** , sélectionnez **Publier la topologie** et exécutez l’Assistant.

