


from ``_GenericLinearTransport__.return_results()``

.. code-block:: python

        conn_arr = self._net.find_connected_pores(self.Ts)
        dx = sp.squeeze(sp.diff(self[self._quantity][conn_arr], n=1, axis=1))
        g = self['throat.conductance']
        rate = sp.absolute(g * dx)
        if 'throat.rate' not in self._phase.props():
            self._phase['throat.rate'] = sp.nan
        self._phase['throat.rate'][throats] = rate[throats]


First the connected pores are found, and then the difference between ``dx`` 
