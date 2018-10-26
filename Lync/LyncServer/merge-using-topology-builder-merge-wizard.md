---
title: Fusion avec l’Assistant Fusion du générateur de topologie
TOCTitle: Fusion avec l’Assistant Fusion du générateur de topologie
ms:assetid: c3f3c425-dab6-4dcd-bf0e-d7fde05f2ebf
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205243(v=OCS.15)
ms:contentKeyID: 49298752
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Fusion avec l’Assistant Fusion du générateur de topologie

 

_**Dernière rubrique modifiée :** 2012-10-02_

1.  Téléchargez le déploiement existant à l’aide du générateur de topologie.

2.  Dans le menu **Action**, sélectionnez **Fusionner Office Communications Server 2007 R2**.

3.  Cliquez sur **Suivant**.

4.  Dans **Spécifier la configuration Edge**, cliquez sur **Ajouter**.
    
    ![Assistant Topologie de la fusion, page Spécifier la configuration Edge](images/JJ205243.cdca609d-d4d5-47d9-9ff8-8b1daa4106e1(OCS.15).jpg "Assistant Topologie de la fusion, page Spécifier la configuration Edge")  

5.  Dans **Spécifier le type Edge**, entrez le type de configuration du serveur Edge, puis cliquez sur **Suivant**. Cet exemple utilise l’option **Serveur Edge unique**.
    
    > [!IMPORTANT]  
    > Un déploiement <strong>Edge étendu</strong> n’est pas une configuration prise en charge. Un serveur <strong>Edge étendu</strong> doit d’abord être converti en <strong>serveur Edge unique</strong> ou <strong>Edge consolidé à charge équilibrée</strong>.

6.  Dans **Spécifier les paramètres Edge internes**, entrez les informations qui conviennent pour le nom de domaine complet interne et les ports du pool Edge si nécessaire, puis cliquez sur **Suivant**.
    
    ![Boîte de dialogue Spécifier les paramètres Edge internes](images/JJ205243.dd664761-839c-4ac8-bd1a-5525589dfbb0(OCS.15).jpg "Boîte de dialogue Spécifier les paramètres Edge internes")  

7.  Dans **Spécifier la configuration Edge externe**, entrez les informations relatives au nom de domaine complet (FQDN) pour votre serveur Edge.
    
    > [!IMPORTANT]  
    > Avant de cliquer sur <strong>Suivant</strong>, effectuez l’étape suivante de cette procédure. Il est très important que vous ne manquiez pas cette étape 11.

8.  Cochez la case **Ce serveur Edge d’accès est utilisé pour la fédération et la solution PIC** si vous planifiez d’utiliser le serveur Edge Office Communications Server 2007 R2 hérité pour la fédération. Si vous avez plusieurs serveurs Edge déployés, un seul d’entre eux est alors activé pour la fédération. Si vous ne cochez pas cette case et que vous décidez d’activer plus tard une fédération, vous devez réexécuter l’Assistant Fusion du générateur de topologie et republier votre topologie.
    
    ![Boîte de dialogue Serveur Edge, page Spécifier la configuration Edge externe](images/JJ205243.32e97ce5-92f0-477e-8125-5d2ece237b13(OCS.15).jpg "Boîte de dialogue Serveur Edge, page Spécifier la configuration Edge externe")  

9.  Dans **Spécifier le tronçon suivant**, entrez le nom de domaine complet (FQDN) de l’emplacement du tronçon suivant dans votre environnement. Cliquez sur **Terminer**.
    
    ![Boîte de dialogue Serveur Edge, page Spécifier le tronçon suivant](images/JJ205243.e734ee0d-f91c-4f3f-8ae6-248ecabcf678(OCS.15).jpg "Boîte de dialogue Serveur Edge, page Spécifier le tronçon suivant")  

10. Dans **Spécifier la configuration Edge**, si tous vos serveurs Edge Office Communications Server 2007 R2 ont été ajoutés, cliquez sur **Suivant**. Si vous avez d’autres serveurs Edge Office Communications Server 2007 R2 à ajouter, répétez la procédure depuis l’étape 4.

11. Dans **Spécifier le port SIP interne**, sélectionnez le paramètre par défaut (c’est-à-dire si vous n’avez pas changé le port SIP par défaut). Au besoin, effectuez la modification si le port par défaut n’est pas 5061, puis cliquez sur **Suivant**.

12. Dans **Sommaire**, cliquez sur **Suivant** pour commencer à fusionner les topologies.

13. La page de l’Assistant vérifie que la fusion des topologies a réussi.

14. Dans la colonne **Statut**, vérifiez que la valeur est **Opération réussie**, puis cliquez sur **Terminer**.

15. Dans le volet gauche du générateur de topologie, vous devriez maintenant avoir **BackCompatSite**, ce qui indique que votre environnement Office Communications Server 2007 R2 a bien été fusionné avec Lync Server 2013.
    
    ![Le Générateur de topologie montrant une fusion de topologie](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Le Générateur de topologie montrant une fusion de topologie")  

16. Dans le menu **Actions**, cliquez sur **Publier la topologie**, puis cliquez sur **Suivant**.

17. Quand l’**Assistant Publication** est terminé, cliquez sur **Terminer**.
    
    > [!NOTE]  
    > Il est important que vous lisiez la rubrique suivante, <a href="import-policies-and-settings.md">Importation des stratégies et des paramètres</a>, car cela permet de s’assurer de l’importation des paramètres de stratégie hérités dans Lync Server 2013.
