---
title: Connexion à Lync 2013 et utilisation sur l’ordinateur virtuel
TOCTitle: Connexion à Lync 2013 et utilisation sur l’ordinateur virtuel
ms:assetid: 6140fc19-5bef-4b58-9b0f-19112b5ecd00
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204948(v=OCS.15)
ms:contentKeyID: 49297378
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Connexion à Lync 2013 et utilisation sur l’ordinateur virtuel

 

_**Dernière rubrique modifiée :** 2012-10-03_

Une fois le plug-in VDI activé, les étapes suivantes se produisent lorsque l’utilisateur se connecte à Lync 2013.

1.  L’utilisateur tape ses informations d’identification dans le client Lync 2013 en cours d’exécution sur l’ordinateur virtuel.

2.  Lorsque Lync détecte la disponibilité du plug-in VDI, Lync invite l’utilisateur à entrer de nouveau ses informations d’identification. Dans cette boîte de dialogue, nous recommandons à l’utilisateur d’activer la case à cocher **Enregistrer mon mot de passe** afin qu’il n’ait pas à les entrer de nouveau lors de connexions ultérieures.

3.  Lync commence le jumelage avec le plug-in VDI. Avant la fin de l’opération de jumelage, le client affiche deux icônes dans la barre d’état Lync. L’icône en bas à gauche indique qu’aucun périphérique audio n’est disponible, tandis que l’icône qui clignote en bas à droite indique que le jumelage VDI est en cours, comme indiqué :
    
    ![Icône Lync VDI indiquant un jumelage réussi](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Icône Lync VDI indiquant un jumelage réussi")  

4.  Une fois le jumelage VDI réussi, les icônes changent pour indiquer le périphérique audio qui sera utilisé pour les appels et la réussite du jumelage VDI :
    
    ![Icône de jumelage Lync VDI indiquant un succès](images/JJ204948.57be3387-a3e5-4949-831e-f5ff9fcc5598(OCS.15).png "Icône de jumelage Lync VDI indiquant un succès")  

5.  Une fois que Lync est jumelé avec le plug-in VDI, l’utilisateur peut voir sa présence sur les périphériques compatibles Lync connectés à l’ordinateur local. L’utilisateur peut alors passer et recevoir des appels comme d’habitude.

