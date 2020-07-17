---
title: Fusion à l’aide de l’Assistant Fusion du générateur de topologie
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Merge using Topology Builder Merge wizard
ms:assetid: c3f3c425-dab6-4dcd-bf0e-d7fde05f2ebf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205243(v=OCS.15)
ms:contentKeyID: 48185343
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4760dcd8810d12b112c3bb042e0f28a039683a08
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757045"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="merge-using-topology-builder-merge-wizard"></a>Fusion à l’aide de l’Assistant Fusion du générateur de topologie

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-02_

1.  Téléchargez le déploiement existant à l’aide du Générateur de topologie.

2.  Dans le menu **Action**, sélectionnez **Fusionner Office Communications Server 2007 R2**.

3.  Cliquez sur **Suivant**.

4.  Dans **Spécifier la configuration Edge**, cliquez sur **Ajouter**.
    
    ![Assistant fusion de topologies, spécifier la page Configuration du serveur Edge](images/JJ205243.cdca609d-d4d5-47d9-9ff8-8b1daa4106e1(OCS.15).jpg "Assistant fusion de topologies, spécifier la page Configuration du serveur Edge")  

5.  Dans **Spécifier le type Edge**, entrez le type de configuration du serveur Edge, puis cliquez sur **Suivant**. Cet exemple utilise l’option **Serveur Edge unique**.
    
    <div>
    

    > [!IMPORTANT]  
    > Un déploiement <STRONG>Edge étendu</STRONG> n’est pas une configuration prise en charge. Un serveur <STRONG>Edge étendu</STRONG> doit d’abord être converti en <STRONG>serveur Edge unique</STRONG> ou <STRONG>Edge consolidé à charge équilibrée</STRONG>.

    
    </div>

6.  Dans **spécifier les paramètres Edge internes** , entrez les informations pertinentes pour le nom de domaine complet interne et les ports du pool Edge si nécessaire, puis cliquez sur **suivant**.
    
    ![Boîte de dialogue spécifier les paramètres Edge internes](images/JJ205243.dd664761-839c-4ac8-bd1a-5525589dfbb0(OCS.15).jpg "Boîte de dialogue spécifier les paramètres Edge internes")  

7.  Dans **Spécifier la configuration Edge externe**, entrez les informations relatives au nom de domaine complet (FQDN) pour votre serveur Edge.
    
    <div>
    

    > [!IMPORTANT]  
    > Avant de cliquer sur <STRONG>Suivant</STRONG>, effectuez l’étape suivante de cette procédure. Il est très important que vous ne manquiez pas cette étape 11.

    
    </div>

8.  Activez la case à cocher **ce pool Edge est utilisé pour la Fédération et la connectivité PIC** si vous envisagez d’utiliser le serveur Edge Office Communications Server 2007 R2 hérité pour la Fédération. Si vous avez plusieurs serveurs Edge déployés, un seul d’entre eux est alors activé pour la fédération. Si vous ne cochez pas cette case et que vous décidez d’activer plus tard une fédération, vous devez réexécuter l’Assistant Fusion du Générateur de topologie et republier votre topologie.
    
    ![Boîte de dialogue serveur Edge, spécifier la page Edge externe](images/JJ205243.32e97ce5-92f0-477e-8125-5d2ece237b13(OCS.15).jpg "Boîte de dialogue serveur Edge, spécifier la page Edge externe")  

9.  Dans **Spécifier le tronçon suivant**, entrez le nom de domaine complet (FQDN) de l’emplacement du tronçon suivant dans votre environnement. Cliquez sur **Terminer**.
    
    ![Boîte de dialogue serveur Edge, spécifier la page du tronçon suivant](images/JJ205243.e734ee0d-f91c-4f3f-8ae6-248ecabcf678(OCS.15).jpg "Boîte de dialogue serveur Edge, spécifier la page du tronçon suivant")  

10. Dans **spécifier la configuration Edge**, si tous vos serveurs Edge Office Communications Server 2007 R2 ont été ajoutés, cliquez sur **suivant**. Si vous avez d’autres serveurs Edge Office Communications Server 2007 R2 à ajouter, répétez cette procédure en commençant à l’étape 4.

11. Dans **spécifier le port SIP interne** , sélectionnez le paramètre par défaut (autrement dit, si vous n’avez pas modifié le port SIP par défaut). Au besoin, effectuez la modification si le port par défaut n’est pas 5061, puis cliquez sur **Suivant**.

12. Dans **Sommaire**, cliquez sur **Suivant** pour commencer à fusionner les topologies.

13. La page de l’Assistant vérifie que la fusion des topologies a réussi.

14. Dans la colonne **Statut**, vérifiez que la valeur est **Opération réussie**, puis cliquez sur **Terminer**.

15. Dans le volet gauche du générateur de topologie, vous devez maintenant voir la **BackCompatSite**, qui indique que votre environnement Office Communications Server 2007 R2 a été fusionné avec Lync Server 2013.
    
    ![Générateur de topologies affichant une topologie fusionnée](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Générateur de topologies affichant une topologie fusionnée")  

16. Depuis le menu **Actions**, cliquez sur **Publier la topologie**, puis sur **Suivant**.

17. Une fois l’**Assistant Publication** terminé, cliquez sur **Terminer**.
    
    <div>
    

    > [!NOTE]  
    > Il est important que vous terminiez la rubrique suivante, <A href="import-policies-and-settings.md">importer des stratégies et des paramètres</A>pour vous assurer que les paramètres de stratégie hérités sont importés dans Lync Server 2013.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

